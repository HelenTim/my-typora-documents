# JS-技巧-3

[toc]

## 在「模版字符串」中可以使用表达式

```jsx
mounted() {
  console.log(`B${this.number || ""} mounted`);
},
```

- 第 2 行，在 `${}` 中可以使用表达式来返回值，而不一定只传入一个变量。

## 解构赋值时可以使用后备值和重命名

它同样开启了 prop 重命名等其它可能，例如将 `user` 重命名为 `person`：

```jsx
<current-user v-slot="{ user: person }">
  {{ person.firstName }}
</current-user>
```

- 通过 `:` 就能够实现重命名

你甚至可以定义后备内容，用于插槽 prop 是 undefined 的情形：

```jsx
<current-user v-slot="{ user = { firstName: 'Guest' } }">
  {{ user.firstName }}
</current-user>
```

- 通过 `=` 可以实现当没有这个属性时的默认值（也可以称为后备值）