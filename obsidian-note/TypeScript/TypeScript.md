#TS

+ [[泛型]]
	+ [[泛型#^979db6|TSX中使用泛型]] 
+ [[内置类]]
+ [[声明文件|声明文件 d.ts]]
	+ [[声明文件#^c096b2|扩展已有模块]]
+ [[语法]]
## 好用的第三库
+ [utility-types](https://github.com/piotrwitek/utility-types)
+ [ts-toolbelt](https://github.com/millsp/ts-toolbelt)

## 获取类的构造函数类型
```ts
class Manager {
	static nick: string;
	method() {
		const nick = (this.constructor as typeof Manager).nick;
	}
}
```

## 获取构造函数的参数
```ts
ConstructorParameters<Type>
```