# typescript-study

private 및 public이 property 뿐만 아니라 method 에서도 작동함.
protected ?

public: 모든 클래스에서 접근 가능
private: 해당 클래스 내에서만 접근 가능 (자식 클래스에서도 접근 불가)
protected: 해당 클래스와 자식 클래스에서 접근 가능

property 를 read only 로 하면 값은 보여주지만 수정은 불가능하게 만들 수 있음.

type Words = {
[key:string]:string
}

class Dict {
private words : Words
constructor(){
this.words = {}
}
add(word:Word){
if(this.words[word.term] === undefined) {
this.words[word.term] === word.def;
}
}
def(term:string){
return this.words[term]
}
remove(term:string){
if(this.words[term] === undefined ){
console.error("`${term}` doesn't exist in dict!")
}

        }
           static hello(){
            return "hello"
    }

}

class Word {
constructor(
public term : string,
public def : string
) {}
}

const kimchi = new Word("kimchi", " 한국의 음식")

const dict = new Dict()

dict.add(kimchi)
dict.def("kimchi")
Dict.hello()

// type 이 특정 값을 가질 수 있게 하는 alias 들
type Team = "read" | "blue" | "yellow"
type Health = 1 | 5 | 10

// 인터페이스는 오직 오브젝트의 모양을 특정해주기 위한 것
//React.js 이용해 작업할 때 많이 사용!
//다른점은 type 키워드가 interface 키워드보다 활용점이 좋음.
interface Player{
nickname:string;
team:Team
health:Health
}

//type Player = {
//nickname:string,
//팀을 만들어주고싶은데 특정 string 이여야함.
//alias 를 만들어서 특정으로 만들어줄 수 있음.
//team:Team
//health : Health
//}

const jaewoo : Player = {
nickname:"jaewoo",
//특정 색깔이 아닌 type 이 오면 error 나옴.
team:"read",
health:10
}

다형성은 다른 모양의 코드를 가질 수 있게 해주는거임 ..
