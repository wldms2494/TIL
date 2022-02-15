this section i'm gonna start over about coding with Apex based on OOP~~~~yeye it;s basic, but important

OOP - 
i don't know in Salesforce , OOP has same definition with Jave ive learned..
because in Salesforce, Object does mean more like Table sheet not 객체!
Object oriented Programming, the code focuses on describing objects. 
an object can be anything that has unique characteristics, such as person, account, or even a flower
before you can truly understand what object-oriented means, there are two thing that you need to understand
Class and objects!

Class is a blueprint. Objects are based on classes. A class defines a set of characteristics and behaviors that are common to all objects of that class

also it's same
there're
Acces Modifier( public, private !~~!) Methods , Parameters 

oh they you system.debug('what you gonna print') interesting

i'm so trying to get used to use vsCode, and Debug Console but they don;t have cool automation work like IntelliJ!!!!!!!!!!!!!

```
public class Flower{
    
    public static Integer wilt(Integer numberOfPetals){
        if(numberOfPetals >= 1){
            numberOfPetals--;
        }
        return numberOfPetals;
    }
    
    public static void grow(Integer height, Integer MaxHeight){
        height = height +2;
        if(height>=MaxHeight){
            pollinate();
        }
    }
    
    public static void pollinate(){
        System.debug('Pollinating....');
    }
}
```
비슷하쥬?
Flower tulip = new Flower ();
tulip.grow();

Flower rose = new Flower ();
rose.grow();

객체도 똑같이 생성하면 된당 ㅎ
아 발렌타인때 받은 꽃 올려야징

<img src="https://user-images.githubusercontent.com/80088918/154083194-899f69d8-072c-48c7-830d-2c9ad73fa181.png" width=400px>
