# TypeScript


آموزش Angular 8 از مبتدی تا پیشرفته
https://toplearn.com/c/o2Z3


TypeScript
https://toplearn.com/c/j2R

24 videos

5:43:00 hours


tsc -w NameTSFile.ts 
CTRL + C   Exit wathing

interface{
    name : valuo;
}

enum{
    name = valuo,
}

Class{
    name : valuo;
}


---------------------------------------------------------
Video 01




---------------------------------------------------------
Video 02

typescript
    Playground:
    https://www.typescriptlang.org/



---------------------------------------------------------
Video 03

typescript download and install

        1- Globally Installing TypeScript (for all PC):
                        npm install -g typescript

        2- Installing TypeScript just for the project:
                        npm install typescript


Greate typescript file :
            main.ts


TypeScript Compile (TS file to JS file):
            tsc main.ts

            tsc -w main.ts 
            CTRL + C   Exit wathing


Greate tsconfig for setting TypeScript:
    tsconfig.json

    in tsconfig.json:
    {
    "compilerOptions": {
        "target": "ES5"
    }
}


---------------------------------------------------------
Video 04




---------------------------------------------------------
Video 05

Types in TypeScript:

    1- String
    2- Number
    3- Boolean
    4- Any


EXA-0

var fName : string;
var lName : string="Rahimi";
var age :number= 33;
var isMale : boolean= true;
var city : string;


EXA-1

function totalLength(x :string, y : string) 
{
    let total = x.length + y.length;
    return total;
}


EXA-2

function totalLength(x :any[], y : string) 
{
    let total = x.length + y.length;
    return total;
}


EXA-3

function totalLength(x :string, y : string) : string
{
    let total = x.length + y.length;
    return total.toString();
}


---------------------------------------------------------
Video 06

Union Type

x :string | any[]
y : string | any[]

 | eller


function totalLength(x :string | any[], y : string | any[]) :number
{
    let total:number = x.length + y.length;
    x.slice(0);
    if( x instanceof Array){
        alert("Type is Array")
    }
    if( x instanceof String){
        alert("Type is String ")
    }
    return total;
}

var person = ['Ali', "Nori", 24, "Gothenbirg"]

totalLength(person,'Ali')


---------------------------------------------------------
Video 07

Function Overload

EXA-1

function sum (x:string, y:string, c:string):string
function sum (x:string, y:string):string
{
    return x +" "+ y;
}



EXA-2
function totalLength(x:string, y:string): number
function totalLength(x:any[], y:any[]): number
function totalLength(x:string | any[], y:string| any[]): number
{
    var total : number = x.length + y.length;
    return total
}




---------------------------------------------------------
Video 08

Interface 

Interface NameInterface{
    NameProperty : TypeProperty;
    name : string;

    age ? : string;
    this's ok if inderface har not age property 
}



EXA-1 

interface IPersen{
    name: string;
    family: string;
    age: number;
    email?: string;
}


function register(person: IPersen)
{
    console.log(person.name + " " + person.family +" , " + person.age);
}

var Iman: IPersen ={
    name:"Iman",
    family:"Madaeny",
    age:30
}


EXA-2

interface IPpesonService{
    add(person:IPersen):IPersen;
    delete(person:IPersen):void;
    getAll():IPersen[];
    getById(personId: number):IPersen;
}

---------------------------------------------------------
Video 09

Enum

enum NameEnum {
    name = valuo,
    name,
}



EXA-1

enum Dags{
    lördag = 1,
    söndag = 6,
    måndag =3,
    tisdag = 433,
    fridag
}

console.log(Dags.tisdag);
console.log(Dags[6]);



EXA-2

enum Colors{
    Red = "#2418014",
    Greed = "#75837",
    Yellow = "#f292084",
}

console.log(Colors.Greed);



EXA-3

interface IPersen{
    name: string;
    family: string;
    age: number;
    gender:Gender;
    email?: string;
}

enum Gender{
    Male = "Sir",
    Female = "Ma'am",
}

function register(person: IPersen)
{
    console.log(person.gender+", "+person.name + " " + person.family +" , " + person.age);
}

var Iman: IPersen ={
    name:"Iman",
    family:"Madaeny",
    age:30,
    gender:Gender.Male
}

function SayHello(type: Gender)
{
    if(type === Gender.Male){
        console.log("Hello Male");
        
    }else{
        console.log("Hello Female");
    }
}

console.log(SayHello(Gender.Male));
EXA-4



---------------------------------------------------------
Video 10

Anonymous Types

var NameAnonymousTypes : { propertyName: propertyType};



EXA-1

var todo : { name: string};

todo = {
    name: "Hafiz"
}
console.log(todo);



EXA-2

function totalLength(x: {len:number}, y:{len: number}):number
{
    var total: number = x.len + y.len;
    return total
}

var x ={
    len:10
}

console.log(totalLength(x,x));



EXA-3

function Login (login:{userName:string, password: number}):void
{
    console.log(login.userName);
    console.log(login.password);
    
}

var hamid ={
    userName: "Hamid Gozug",
    password:36463746,
}

Login(hamid)


---------------------------------------------------------
Video 11

Class in TypeScript

class NameClass{
    constructor(){}

    NameProperty : TypeProperty;
    name : string;
}

var varNeme = new NameClass()



EXA-1

class Person{

    constructor(){
        this.name = "Hamid";
        this.family= "golabi"
    }

    name : string;
    family:string;
}


function Resgister (person: Person)
{
    console.log(person.name + " " + person.family);
}

var iman = new Person();

Resgister(iman)



EXA-2

class Person{

    constructor(name: string, family:string){
        this.name = name;
        this.family= family;
    }

    name : string;
    family:string;

}


function Resgister (person: Person)
{
    console.log(person.name + " " + person.family);
}

var iman = new Person("Iman", "Madaeny");

Resgister(iman)




EXA-3

class Person{

    constructor(name: string, family:string){
        this.name = name;
        this.family= family;
    }

    name : string;
    family:string;

    FullName = function ():string
    {
        return this.name + " " + this.family;
    }
}


function Resgister (person: Person)
{
    console.log(person.name + " " + person.family);
}

var iman = new Person("Iman", "Madaeny");

Resgister(iman)

console.log(iman.FullName());


---------------------------------------------------------
Video 12

Static Members

varName.propertyName= valuo;
    iman.name= "Hamid";

Static NameStatic : typeStatic = valuoStatic;
    static lastId:number = 1;


EXA-1

class Person{

    constructor(name: string, family:string){
        this.name = name;
        this.family= family;
    }

    name : string;
    family:string;

    FullName = function ():string
    {
        return this.name + " " + this.family;
    }
}

var iman = new Person("Iman", "Madaeny");

iman.name= "Hamid",
iman.family = "Golabi"

console.log(iman.FullName());



EXA-2 (Person.lastId)

class Person{

    static lastId:number = 1;

    constructor(name: string, family:string){
        this.name = name;
        this.family= family;
    }

    name : string;
    family:string;

    FullName = function ():string
    {
        return this.name + " " + this.family;
    }
}


function Resgister (person: Person)
{
    console.log(person.name + " " + person.family);
}

var person1 = new Person("Iman", "Madaeny");
console.log(person1.FullName());
console.log(Person.lastId);


var person2 = new Person("Hamed", "Homayon");
console.log(person2.FullName());
console.log(Person.lastId);

var person3 = new Person("Ali", "Nori");
console.log(person3.FullName());
console.log(Person.lastId);


EXA-3  (Person.getNext();)

class Person{

    static lastId:number = 1;

    constructor(name: string, family:string){
        this.name = name;
        this.family= family;
    }

    name : string;
    family:string;

    FullName = function ():string
    {
        return this.name + " " + this.family;
    }

    static getNext(){
        this.lastId+=1;
    }
}


function Resgister (person: Person)
{
    console.log(person.name + " " + person.family);
}

var person1 = new Person("Iman", "Madaeny");
console.log(person1.FullName());
console.log(Person.lastId);
Person.getNext();


var person2 = new Person("Hamed", "Homayon");
console.log(person2.FullName());
console.log(Person.lastId);
Person.getNext();

var person3 = new Person("Ali", "Nori");
console.log(person3.FullName());
console.log(Person.lastId);
Person.getNext();


---------------------------------------------------------
Video 13

Get and Set


EXA-1

interface Todo{
    name : string;
    state: TodoState;
}

enum TodoState{
    New,
    Active,
    Complete,
    Delete
}

var todo = {
    name: "Bank",
    get state(){
        return this._state;
    },
    set state(newState){
        this._state= newState;
    }
}

// Set
todo.state= TodoState.Complete;

// Get
console.log(todo.state);



EXA-2

class SmartTodo{

    name: string;
    _state: TodoState;

    constructor(name:string){
        this.name = name;
    }
    get state(){
        return this._state;
    },
    set state(newState){

        if(newState == TodoState.Complete)
        {
            var canBeComplete =
            this.state == TodoState.Active || this.state== TodoState.Delete;

            if(!canBeComplete)
            {
                throw "Todo must be Active or Deleted in ..."
            }
        }

        this._state= newState;
    }
}

var todo = new SmartTodo("Bank");
todo.state= TodoState.New;
var st = todo.state;

console.log(st);


---------------------------------------------------------
Video 14

ارث بری در تایپ اسکریپت

1- private
2- extends
3- super

EXA

interface Todo{
    name : string;
    state: TodoState;
}

enum TodoState{
    New,
    Active,
    Complete,
    Delete
}

class TodoStateChanger{
    constructor(private newState: TodoState) {}

    canChangeState (todo:Todo):boolean
    {
        return !!todo;
    }
    changeState(todo:Todo):Todo
    {
        if(this.canChangeState(todo))
        {
            todo.state = this.newState;
        }
        return todo;
    }
}


class CompleteTodoStateChanger extends TodoStateChanger
{
    constructor()
    {
        super(TodoState.Complete)
    }

    canChangeState(todo: Todo):boolean
    {
        return super.canChangeState(todo) && (todo.state == TodoState.Active || todo.state == TodoState.Delete)
    }
}




---------------------------------------------------------
Video 15

abstract class

abstract canChangeState



EXA



interface Todo{
    name : string;
    state: TodoState;
}

enum TodoState{
    New,
    Active,
    Complete,
    Delete
}

abstract class TodoStateChanger{
    constructor(private newState: TodoState) {}

    abstract canChangeState (todo:Todo):boolean;

    changeState(todo:Todo):Todo
    {
        if(this.canChangeState(todo))
        {
            todo.state = this.newState;
        }
        return todo;
    }
}

// var df = new TodoStateChanger(TodoState.Complete);

class CompleteTodoStateChanger extends TodoStateChanger
{
    constructor()
    {
        super(TodoState.Complete)
    }

    canChangeState(todo: Todo):boolean
    {
        return !!todo && (todo.state == TodoState.Active || todo.state == TodoState.Delete)
    }
}





---------------------------------------------------------
Video 16

Access Modifiers اعضای کلاس

1- private 
2- protected 
3- public 





EXA-1

class Person{
    private name: string;
    protected age : number;
    public family:string;
}

var p1 = new Person();

p1.name 

p1.family = 'madaeny'

class Emploee extends Person{
    age: number;
}

var p2 = new Emploee();
p2.age = 22;



EXA-2

class Person{
    private name: string;
    protected age : number;
    public family:string;

    protected getAmount()
    {
        return 1250000;
    }
}

var p1 = new Person();

p1.name 

p1.family = 'madaeny'



class Emploee extends Person{
    age: number;

    public getsalary()
    {
        return this.getAmount;
    }
}

var p2 = new Emploee();
p2.getsalary();




EXA-3

interface Todo{
    name : string;
    state: TodoState;
}

enum TodoState{
    New,
    Active,
    Complete,
    Delete
}

class TodoService{

    private static _lastId: number = 0;

    constructor (private todos:Todo[]){}

    private get nextId(){
        return TodoService.getNextId();
    }

    private set nextId(nextId)
    {
        TodoService._lastId = nextId -1;
    }

    static getNextId()
    {
        return TodoService._lastId+=1;
    }

    add(todo: Todo)
    {
        var newId=this.nextId;
    }

    private  getAll()
    {
        return this.todos;
    }
}


---------------------------------------------------------
Video 17

1- class TodoService implements ITodoService, IIdGenerator



1- File model.ts

interface ITodoService
{
    add(todo: Todo):Todo;
    delete(todoId: number):void;
    getAll():Todo[];
    getbyId(todoId: number):Todo;
}

interface Todo{
    id:number;
    name : string;
    state: TodoState;
}

enum TodoState{
    New = 1,
    Active,
    Complete,
    Delete
}



2- File TodoService.ts

interface IIdGenerator{
    nextId:number;
}


class TodoService implements ITodoService, IIdGenerator {

    private static _lastId: number = 0;

    constructor (private todos:Todo[]){}

    get nextId(){
        return TodoService.getNextId();
    }

    static getNextId()
    {
        return TodoService._lastId+=1;
    }

    add(todo: Todo):Todo
    {
        todo.id= this.nextId;
        this.todos.push(todo);
        return todo;
    }
    delete(todoId: number)
    {
        var toDelete= this.getbyId(todoId);
        var deletedindex = this.todos.indexOf(toDelete);
        this.todos.splice(deletedindex, 1);
    }
    getAll()
    {
        return this.todos;
    }
    getbyId(todoId: number):Todo
    {
        var filter = this.todos.filter(x=> x.id==todoId);
        if(filter.length)
        {
            return filter[0]
        }
        return null;
    }
}



3- File TodoStateChanger.ts

abstract class TodoStateChanger{
    constructor(private newState: TodoState) {}

    abstract canChangeState (todo:Todo):boolean;

    changeState(todo:Todo):Todo
    {
        if(this.canChangeState(todo))
        {
            todo.state = this.newState;
        }
        return todo;
    }
}

class CompleteTodoStateChanger extends TodoStateChanger
{
    constructor()
    {
        super(TodoState.Complete)
    }

    canChangeState(todo: Todo):boolean
    {
        return !!todo && (todo.state == TodoState.Active || todo.state == TodoState.Delete)
    }
}



---------------------------------------------------------
Video 18

Generic 


1- serialize (Files to jsonFile)
        JSON.Stringify(NameFile)

2- deserialize (jsonFile to Files)
       JSON.parse(NameJsonFile)
 
3- Generic 
    function NameGeneric <TypeGeneri>(){}

4- Generic Class
    class NameClass <TypeGeneri or  Parameter>{}

5- function NameGeneric < >(  extends  ){}




__________________________
EXA-1

function clone<T>(value:T):T
{
    let serialized = JSON.stringify(value);
    return JSON.parse(serialized);
}

clone<number>(222);
clone<string>("Iman");


__________________________
EXA-2

interface Todo{
    id:number;
    name : string;
    state: TodoState;
}

enum TodoState{
    New = 1,
    Active,
    Complete,
    Delete
}

function clone<T>(value:T):T
{
    let serialized = JSON.stringify(value);
    return JSON.parse(serialized);
}


var todo:Todo ={
    id:222,
    name:'Iman',
    state:TodoState.Complete
}

clone<Todo>(todo)


__________________________
EXA-3 (class Generic)

class KeyValuePair <TKey, TValuo>{
    constructor(public key:TKey , public value:TValuo){}
}

let pair1= new KeyValuePair<number,string>(1,'First');
let pair2= new KeyValuePair<string,Date>("Second",new Date(Date.now()));
let pair3= new KeyValuePair<number,string>(3,'Third');

__________________________
EXA-4

class KeyValuePair <TKey, TValuo>{
    constructor(public key:TKey , public value:TValuo){}
}

let pair1= new KeyValuePair<number,string>(1,'First');
let pair2= new KeyValuePair<string,Date>("Second",new Date(Date.now()));
let pair3= new KeyValuePair<number,string>(3,'Third');

class KeyValuoPairPrinter<T,U>{
    constructor(private pairs: KeyValuePair<T,U>[]){}

    print()
    {
        for(let p of this.pairs)
        {
            console.log(`${p.key} : ${p.value}`);
            
        }
    }
}

var printer = new KeyValuoPairPrinter([pair1,pair3]);

printer.print();


__________________________
Greate KeyValuoPairPrinter.ts

class KeyValuePair <TKey, TValuo>{
    constructor(public key:TKey , public value:TValuo){}
}


class KeyValuoPairPrinter<T,U>{
    constructor(private pairs: KeyValuePair<T,U>[]){}

    print()
    {
        for(let p of this.pairs)
        {
            console.log(`${p.key} : ${p.value}`);
            
        }
    }
}


__________________________
EXA-5  (extends)

function totalLength(x:{length: number}, y:{length: number}) 
{
    var total : number = x.length + y.length;
    return total;
}

var length = totalLength('Joe',[2,3,4,5]);

console.log(length);


======= With extends  ==========>>>>>>

function totalLength<T extends {length:number}>(x:T, y:T) 
{
    var total : number = x.length + y.length;
    return total;
}

var length = totalLength('Joe','Amiri');

console.log(length);


======= With extends GoodCode ==========>>>>>>

interface IHaveALength{
    length:number;
}


function totalLength<T extends IHaveALength>(x:T, y:T) 
{
    var total : number = x.length + y.length;
    return total;
}

var length = totalLength('Joe','Amiri');

console.log(length);

---------------------------------------------------------
Video 19

Modules

1- namespace name.OneDel{}
    namespace TodoApp.Model{}

2- export
    export interface Todo{}

3- inport
    import Todo1 = TodoApp.Model.Todo



EXA
In model.ts

namespace TodoApp.Model{
    
    export interface Todo{
        id:number;
        name : string;
        state: TodoState;
    }

}

namespace TodoApp.Model{
    
    export enum TodoState{
        New = 1,
        Active,
        Complete,
        Delete
    }

}

namespace DataAccess{

    import Model = TodoApp.Model;
    import Todo = Model.Todo;

    // import Todo1 = TodoApp.Model.Todo

    interface ITodoService
{
    add(todo: Todo):Todo;
    delete(todoId: number):void;
    getAll():Todo[];
    getbyId(todoId: number):Todo;
}
}


namespace Hafiz{

    export enum TodoState{
        New = 1,
        Active,
        Complete,
        Delete
    }

    export interface Todo{
        id:number;
        name : string;
        state: TodoState;
    }

}



---------------------------------------------------------
Video 20

Internal  and External Internals

1- InternalInternal

2- External Module
    export interface Todo{}

    import Model = require("./model");
    import Todo =Model.Todo;




1- tsconfig.json File

{
    "compilerOptions": {
        "target": "ES5",
        "module": "system"
    }
}



2- model.ts File  is External Module

    export interface Todo{
        id:number;
        name : string;
        state: TodoState;
    }
    export enum TodoState{
        New = 1,
        Active,
        Complete,
        Delete
    }



3- DataAccess.ts File is Internal Module

import Model = require("./model");
import Todo =Model.Todo;


    let _lastId: number = 0;
    function generateTodo() {
        return _lastId+=1;
    }

    interface ITodoService{
    add(todo: Todo):Todo;
    delete(todoId: number):void;
    getAll():Todo[];
    getbyId(todoId: number):Todo;
    }
    

class TodoService implements ITodoService{

    constructor (private todos:Todo[]){}

    add(todo: Todo):Todo
    {
        todo.id= generateTodo();
        this.todos.push(todo);
        return todo;
    }
    delete(todoId: number)
    {
        var toDelete= this.getbyId(todoId);
        var deletedindex = this.todos.indexOf(toDelete);
        this.todos.splice(deletedindex, 1);
    }
    getAll()
    {
        return this.todos;
    }
    getbyId(todoId: number):Todo
    {
        var filter = this.todos.filter(x=> x.id==todoId);
        if(filter.length)
        {
            return filter[0]
        }
        return null;
    }
}






---------------------------------------------------------
Video 21

فراخوانی و استفاده از ماژول ها در تایپ اسکریپت

1-  import {} from ''
       import  {Todo, TodoState} from './model';

2-    as in inport (for chanche name)
        import  {Todo as TodoTask, TodoState} from './model';

3- install library systemjs (for loding and add Files ts)
        npm istall systemjs   
        
4- system.js is module loder




EXA-1

import  {Todo, TodoState} from './model';

var t : Todo ={
    id:5,
    name: 'task 1',
    state: TodoState.New
}



EXA-2

import  {Todo as TodoTask, TodoState} from './model';

var t : TodoTask ={
    id:5,
    name: 'task 1',
    state: TodoState.New
}
---------------------------------------------------------
Video 22
Project


---------------------------------------------------------
Video 23
Project


---------------------------------------------------------
Video 24
Project


