##Update

CRUD중 나는 기본 프로젝트 할때에도 수정부분이 어려워서 사질 게시판에 업데이트를 하지 못했다 ;;  

다시 업데이트에 대해서 리마인드 해보아야겠다.  


```java

@PutMapping("/api/comments")  

  public Long updateComment(@RequestBody CommentRequestDto requestDto,
  @AuthenticationPrincipal UserDetailsImpl userDetails)   
{
 return commentService.update(requestDto, userDetails);

    }

```

- controller부분  
  "PUT"타입으로 "/api/comments"로 들어오면 일단,
  컨트롤러에서는 update를 거의 처리 하지 않고, service로 보낸다.  
  사용자가 입력한 정보를 가져와야하지 @RequestBody를 통해 제이슨 형식의 데이터를 가져오고, 이정보는 requestDto를 거쳐서 들어오게 된다.
  @AuthenticationPrincipal 을 통해 로그인된 사용자 입력 정보도 함께 들어오게 된다.
        근데 왜 Long 타입일까..? 고민해봐야 할 부분이다.****

    여기서 CommentRequesdto로 들어 오는것은 변경하는 내용이다 
a를 b로 변경한다면, b가 지금 requestDto로 들어오게 되는것이다.


- 여기서 궁금한 부분! 예전 update를 만들때는 수정되는 글의 아이디 값을 같이 들고와서 url을 "/api/comments/{id}"해서 파라밑어
넣는 곳에다가 @Pathvariable을 통해 Long id를 가져 왔는데, 여기 코멘트 수정하는 부분은 아 쓰다 보니까  
 function editComment(id)를 보면 id를 가져와서 url로 쏘아 올리지 않고, data값을 통해서 가져왔다.
  let data = {'id': id, 'content': contents};
 그래서 여기 requestDto에는 위의 데이터인 postId값과, 댓글의 내용content 두가지 내용을 담고 있고,   
 정리하자면 여기 메소드에서는 commment의 content와 postId와 userDetail댓글 작성자의 정보를 담고 있는 것이다.
 이것을 다시 service로 넘겨 주자 !

********************윗부분은 내가 잘못생각했다.  
지금 들고온 requestDto는 아이디값과, content를 가지고 있는데 여기서 id값은 postId가 아니라 코멘트의 id값이다.
어떻게 이렇게 되었냐?

자바스크립트를 다시 가져와보면 우리가 addHTMl을 하는 과정에 있어서 append를 html에 표시하고 있다.

이부분은 진짜 사실 좀 복잡하긴 하다;

코드 한줄로 일단
```java
 <button id = "${id}-delete"  onclick="deleteComment(${commentList[i]['id']})">댓글삭제</button>
```

이곳을 통해 나는 일반 {id} 포스트 아이디가 아닌, 딜리트 함수를 실행할때 들어가는 파라미터 값 확인해봐라  
comment의 id값을 들고 올 수 있었다.


```java


@Transactional
public Long update(CommentRequestDto requestDto, UserDetailsImpl userDetails) {
        Comment comment = commentRepository.findById(requestDto.getId()).orElseThrow(
        ()->new IllegalArgumentException("해당아이디가 없습니다")
        );
        if(comment.getUserId().equals(userDetails.getUser().getId())) {
        comment.setContent(requestDto.getContent());//여기가 무슨일 하는지 모르겠음
        commentRepository.save(comment);
        }

        return 1L;



```

update의 1번 과정 !  
변경 하고 싶은 데이터의 아이디값을 먼저 들고와야겠죠?  무엇을 변경할지는 결정해야 update가 가능하니,  
그것을 처리해주는 코드가 이것이다.  
```js
     Comment comment = commentRepository.findById(requestDto.getId()).orElseThrow(
        ()->new IllegalArgumentException("해당아이디가 없습니다")
```

그리고 해당아이디가 없을 경우의 예외 처리도 꼭 해줘야 한다. 어떻게 여기 값이 null이 될수 있지라는 의문이 들지만,  
컴퓨터는 바보라.. 넣어 줘야한다 이부분은 너무 파려고 하지 말자;

이렇게 코멘트를 가져 왔다. 내가 변경하고 싶은 코멘트의 아이디 값을 통해서 comment를 가져 오고,   
이제 거기에 무슨 내용을 넣을지가 필요 하겠지?  
여기서 사용 되는 것 코드
```java
 comment.setContent(requestDto.getContent());//여기가 무슨일 하는지 모르겠음
```

아이디를 통해 해당 comment를 가져오고, 거기에다가 set을 통해 content를 셋팅?주입?시키고 여기서 주입되는 content는 , 
requestDto사용자가 입력값에서,getContent를 통해 content만을 가져 온것이다.

이렇게 정성스럽게 탄생한 comment는 save를 통해 commentRepository에 다시 넣어 준다.

return값은 아무 값이나? 빼줘도 되기 때문에 랜덤으로 그냥 1L 라고 아이디 값을 빼주었다.


마지막으로 댓글의 작성자가 아닌 사람은 해당 댓글을 수정하지 못하게 하는 코드를 리뷰해보자 !

```java
    if(comment.getUserId().equals(userDetails.getUser().getId())) {
            comment.setContent(requestDto.getContent());//여기가 무슨일 하는지 모르겠음
```
comment작성자를 getUserId()를 통해서 뽑아온다.  
그리고 userDetails즉 지금 현재 로그인 된 사용자를 getUser로 뽑아오고, getId를해서 사용자의 Id를 뽑아온다.

이렇게 comment작성자의 Id와 현재 로그인된 사용자의 Id가 일치 하면,  
comment에다가 setContent의 내용을 셋팅 해준다.  
else문을 통해서 반대과정도 처리 하고 싶으나 어떻게 해야할지 잘 모르겠다.
else해서 alert를 통해 "해당 댓글을 수정할 수 없습니다 " 해주고싶은데 음 아직은 잘 모르겠네
sout을 뿌려줄수도 없고;;허허 이렇게 하면 사용자 쪽에서 확인이 안되자냐...






