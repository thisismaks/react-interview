## TypeScript
### Structure vs Nominative
дописать ?

### Утилитарные типы?
- Partial<Type> ​
- Required<Type> ​
- Readonly<Type> ​
- Record<Keys, Type> ​
- Exclude<UnionType, ExcludedMembers> ​
- Extract<Type, Union> ​
- Pick<Type, Keys> ​
- Omit<Type, Keys>

### Отличие type от interface?
Интерфейсы мержаться и наследуются.

Что может тип что не может интерфейс?
Абстрактный класс?

дописать

### Отличие never от void?
void - функция, возвращающая undefined  
never - функция не доводящая до return.

### Что такое дженерик?
Позволяет создавать гибкие переиспользуемые типы и определять тип в момент использования. Результирующий тип в зависимости от входного типа. Аналогия с функциями.

### Пример MyPick?
```JS
type MyPick<T, Key extends keyof T> = { [k in Key]: T[k] }
```

### Пример "условие"
```JS
type If<C extends Boolean, T, F> = C extends true ? T : F;

type A = If<true, 1, 2>
type B = If<false, 1, 2>

type C = If<null, 1, 2>
```

### Пример "concat"
```JS
const tuple = [1] as const;

type Concat<T extends readonly unknown[], U extends readonly unknown[]> = [...T, ...U];
type Arr1 = Concat<[1],[2]>
type Arr2 = Concat<typeof tuple,[2]>
```
