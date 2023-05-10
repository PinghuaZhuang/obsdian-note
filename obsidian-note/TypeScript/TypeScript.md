#TS

+ [[泛型]]
	+ [[泛型#^979db6|TSX中使用泛型]] 
+ [[内置类]]
+ [[声明文件|声明文件 d.ts]]
	+ [[声明文件#^c096b2|扩展已有模块]]
+ [[语法]]

## [[JSDoc#代码提示配置]]

## 好用的第三库
+ [utility-types](https://github.com/piotrwitek/utility-types)
+ [ts-toolbelt](https://github.com/millsp/ts-toolbelt)
[参考文档](https://juejin.cn/post/7211358106629750841?utm_source=gold_browser_extension)

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

## Infer
infer推导的名称相同并且都处于***逆变***的位置，则推导的结果将会是交叉类型。
```ts
type Bar<T> = T extends {
  a: (x: infer U) => void;
  b: (x: infer U) => void;
} ? U : never;

// type T1 = string
type T1 = Bar<{ a: (x: string) => void; b: (x: string) => void }>;

// type T2 = never
type T2 = Bar<{ a: (x: string) => void; b: (x: number) => void }>;
```
infer推导的名称相同并且都处于***协变***的位置，则推导的结果将会是联合类型。
```ts
type Foo<T> = T extends {
  a: infer U;
  b: infer U;
} ? U : never;

// type T1 = string
type T1 = Foo<{ a: string; b: string }>;

// type T2 = string | number
type T2 = Foo<{ a: string; b: number }>;
```