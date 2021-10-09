##Delete

딜리트 함수 찢어보기
===========
딜리트 하는 api만들기


스프링 기초반에서 delete퀴즈 부분 ! 이제 이해를 좀 하겠군 

```java
@DeleteMapping("/api/courses/{id}")
public Long delete (@Pathvariale Long id) {

coursesRepository.deleteById(id)
        return id;
}
```
삭제를 하려면 아무 코스나 삭제 할 수 없으니깐, 해당 게시글의 id값을 함께 가져와야 하지 않을까?
그리고 이 메소드는 아이디를 파라미터로 가져 오는 메소드이니 자료형태?를 Long으로 해줘야 할것 같다.   
그  다음 url을 통해서 들고온 id값을,
@Pathvariable을 통해서 id값을 파라미터로 가져와준다. 아이디값은 url에서 혼자 뚝 떨어지지 않는다.  
그리고 repository에 가서 deleteById (이것은 JpaRepository에서 나온것임)아이디를 통해서 삭제 하는것이니   
아이디 값을 넣어줘야겟죠? 그래서deleteById(id)라고 써준닷ㅎ
그리고 마지막으로 return courseRepository.deleteById(id)이렇게 끝을 내버리면 
사실 deleteById는 반환하는 값이 아예 없기 때문에 에러가 난다. 이렇게 상식적으로 생각해보면 좀 쉬운것 같다.
그래서 그냥 return으로 id;를 써주자 !


이제 나의 과제 리뷰를 해보잣 

위의 형식은 이제 보니 꽤나 간단해 보인다.   
하지만 이번의 나의 코멘트 부분은 꽤나 복잡했기 때문에  
controller에서 service로 넘겨 주는게 이상적이지만;;


controller에 모든것을 처리해보고 말았구나.

강의를 다시 듣고 리펙토링 하는 과정이 필요할듯하다.;;


-컨트롤러 부분


```java
@DeleteMapping ("/api/comments/{id}")
public Long delete(@Pathvarialbe Long id) {  
    commentRepository.deleteById(id)
        return id;
        }
```

이게 지금 내머리속에서 나온거.. ;; 현실은


```java
 @DeleteMapping("/api/comments/{id}")
    public Long deleteComment(@PathVariable Long id, @AuthenticationPrincipal UserDetailsImpl userDetails) {
        System.out.println("카멘트딜리트테스트");

        Comment comment = commentRepository.findById(id).orElse(null);
        Blog blog = blogRepository.findById(comment.getPostId()).orElse(null);
        if (comment.getUserId().equals(userDetails.getUser().getUsername())) {

            blog.getCommentList().remove(comment);
            commentRepository.deleteById(id);
        }
        return id;
    }
}
```

url을 통해 아이디를 들고오는것 까지는 맞았다!


**여기서 포인트 !*  
여기 url에 들어있는 "/api/comments/id"는 comment의 id이다 . postid값이 들어오면
내가 댓글 삭제 버튼을 눌렀을때 해당 댓글의 아이디가 아니라 다른 아이디를 가르켜서 괜히 쌩뚱맞은 댓글이 지워질 수 도 있다.
하하하하하    
아무 댓글을 지워 버릴순 없으니까 내가 지울 게시글을에 대한 point가 필요하다.
그리고 그 id값은 그냥 파라미터 값에 넣는다고 위의 url에 뚝 떨어지는 것이 아니다.  
**@Pathvariable**을 통해서 url에서 아이디 값을 들고 와준다. 
그리고 해당 게시물을 아무나 삭제 할수 없도록 로그인된 사용자와 코멘트 작성자의 아이디를 비교 하기 위해, 파라미터로, UserDetails까지 들고 와줬다.

```        System.out.println("카멘트딜리트테스트");```  

이 부분은 딜리트가 처음에 너무 안되서 시험용으로 여기 함수까지는 지금 아이디가 도착은 했나 싶어서 심어준 테스트 한줄이다.

그 다음에는 update부분이랑 비슷하다. 해당 댓글의 아이디를 들고왔으면,
그 아이디에 맞는 comment를 찾는 작업이 필요하겠지?

commentRepo를 가서 받은 아이디의 값을 통해 댓글을 찾아 와야 한다.  
```Comment comment = commentRepository.findById(id).orElse(null);```

그 다음에는 update부분이랑 비슷하다. 해당 댓글의 아이디를 들고왔으면,
그 아이디 값에 맞는 댓글을 Repository에서 찾아와서 그 comment를 생성 해준다.
삭제할 내용이 있어야 삭제가 가능한것이 아닌가. 항상 코드를 쓸때는 생각을 좀 하고 써야겠다.
그리고 컴퓨터는 바보라서 이 아이디값이 없을때의 경우까지 처리 해줘야 하니깐. orElse(null)을 통해  
예외 처리를 해준다.

진짜 승준님 아니였으면 생각 못했을 부분
============
이제 진짜 내가 찐으로 생각하지 못했던 부분을 적어 보겠다.  
사실상 여기 댓글이 보여짐이 가능했던 부분은
코멘트 테이블 때문이 아니라,  
블로그 테이블에 연관관계를 맺어줘서  
블로그 테이블을 통해 getMapping을 해줘서 사용자들에게 뿌려줬다.  
*getMapping*을 다시 상기시켜 보자.


```java
  @GetMapping("/api/comments")
    public List<Comment> getComment() {
        return commentRepository.findAll();
    }

```
여기서 List<Comment>는 comment테이블에서 온것이 아니라, 
블로그 테이블에서 우리가 코멘트와 연관관계를 맺어주었던


````java

@Getter
@NoArgsConstructor
@Entity//테이블 생성
public class Blog extends Timestamped{


    //전역변수 (블록에 같혀져있지 않음. 프로그램이 시작되는 시점부터 끝날때까지 사라지지 않음)
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    private Long id;

    @Column(nullable = false)
    private String title;

    @Column(nullable = false)
    private String username;

    @Column(nullable = false)
    private String content;
    
    @OneToMany
    private List<Comment> commentList;

````
저기 위의 List<Comment>를 뿌려주는 것이다. 그럼으로  
해당 게시글을 일단 들고와야겠지.

``` Blog blog = blogRepository.findById(comment.getPostId()).orElse(null);```
blogRepository 에서 id 값을 통해서 블로그를 찾을껀데, 껀데..  
이 아디값은 코멘트가 써진 포스트의Id를 통해서 블로그를 찾고, 이를 다시 만들어온다?or꺼내 온다.  
하지만 그렇다고 우리가 댓글을 삭제 할꺼지 해당 게시글 삭제를 할수 없지 않느냐    
댓글 삭제를 눌렀는데
해당 게시글이 삭제 되면 너무 어이가 없지 않을까?  
 우리가 지울것은 게시글이 아니라 게시글의 코멘트 리스트의 한 부분이지 않는가?

그래서 blog.getCommentList()를 통해 블로그의 댓글 리스트를 들고오고, 그 다음에  
remove를 할껀데 다 remove할껀 아니지 않냐;;
여기에 이제 우리가 찾아논 comment
댓글 삭제라는 버튼을 눌렀을때 가져와진 코멘트의 아디값을 통해 찾아진 comment를 remove에다가 넣어줘서,  
blog.getCommentList().remove(commet);가 탄생하게 되는 것이다.
그다음dms  
commentRepository에도 삭제가 필요하니
```java
            commentRepository.deleteById(id);

```
jpa를 이용하여 repo에서도 삭제 완료

마지막으로 return값은 아이디로 준다.































