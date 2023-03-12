* REPL
* TypeScript
    - Interface vs Type
    - 타입 추론
    - Union Type vs Intersection Type
    - Optional Parameter

REPL: Read-Eval-Print Loop (CLI or consol 환경) is a computer environment where user inputs are read and evaluated, and then the results are returned to the user. REPLs provide an interactive environment to explore tools available in specific environments or programming languages.

TS node는 직접 설치 필요
TERMINAL:
$ npx ts-node (실행문)
$ npm list -g (global 실행)
ctrl + C , ctrl + D or .exit 으로 나가기

# 타입 지정
let name: string;
name = '홍길동';  //'홍길동'
name = 123  //error TS2322 (맞는 타입만 assign 가능)

예시1)
let human: {
    name: string;
    age: number;
}
human = { name:'홍길동', age: 13 };

error TS2739: missing properties
error TS2322: unknown properties

타입 정의 하기 ( 재사용 )
type human: {
    name: string;
    age: number;
}
      or
Interface human: {
    name: string;
    age: number;
}

human = { name: '홍길동', age: 13}  //{ name: '홍길동', age: 13}

* 타입 정의
function add(x: number, y: number): number{
    return X + Y;
}
add(1,2)  //3 
add('1', 2)  // error TS2345: wrong type(string)

* 값으로 타입을 지정 ( Union )
let category: 'food';
category = 'food';
category = 'book'  //error TS2322 not assignable
category = 'desk'  //error TS2322 not assignable

* 배열(array)로 타입을 정의
let numbers: number[];
numbers = [1,2,3]  //[ 1, 2, 3 ]

* any[] (아무거나 가능) & Tuple (엄격함)
let anythings: any[];
anythings = ['hp', 256]  //[ 'hp', 256]
let pair: [string, number];
pair = ['hp', 256]  //[ 'hp', 256]

# 타입 추론 (assign 된 값으로 type을 추론해줌)
const name: string = '홍길동'
const name = '홍길동' 

# Union Type ( 합집합 )
예) boolean은 true | false
type bool = true | false;
let flag: bool;
flag = true;
flag = false; 
flag = 3;  //error

type Category = 'food' | 'toy' | 'bag'; (정한 type만 가능)
let c: Category;
c = 'food';  //food
c = 'toy';  //toy
c = 'desk';  //error





