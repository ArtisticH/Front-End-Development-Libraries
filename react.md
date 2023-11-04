# React
React is a popular JavaScript library for building reusable, component-driven user interfaces for web pages or applications.

React combines HTML with JavaScript functionality into its own markup language called JSX. React also makes it easy to manage the flow of data throughout the application.  
- "React는 HTML과 JavaScript 기능을 JSX라고 하는 자체 마크업 언어로 결합합니다."
- React는 JSX라는 자체 마크업 언어를 사용하여 HTML과 JavaScript의 기능을 통합하여 UI를 작성합니다.

In this course, you'll learn how to create different React components, manage data in the form of state props, use different lifecycle methods like `componentDidMount`, and much more.  
- React는 데이터의 흐름을 관리하기 쉽게 만들어주며, 애플리케이션 내에서 데이터를 효율적으로 다룰 수 있도록 도와줍니다.  

## Create a Simple JSX Element
React is an Open Source view library created and maintained by Facebook. It's a great tool to render the User Interface (UI) of modern web applications.

React uses a syntax extension of JavaScript called JSX that allows you to write HTML directly within JavaScript. This has several benefits. It lets you use the full programmatic power of JavaScript within HTML, and helps to keep your code readable. For the most part, JSX is similar to the HTML that you have already learned, however there are a few key differences that will be covered throughout these challenges.

For instance, because JSX is a syntactic extension of JavaScript, you can actually write JavaScript directly within JSX. To do this, you simply include the code you want to be treated as JavaScript within curly braces: `{ 'this is treated as JavaScript code' }`. Keep this in mind, since it's used in several future challenges.

However, because JSX is not valid JavaScript, JSX code must be compiled into JavaScript. The transpiler Babel is a popular tool for this process. For your convenience, it's already added behind the scenes for these challenges. If you happen to write syntactically invalid JSX, you will see the first test in these challenges fail.

It's worth noting that under the hood the challenges are calling `ReactDOM.render(JSX, document.getElementById('root'))`. This function call is what places your JSX into React's own lightweight representation of the DOM. React then uses snapshots of its own DOM to optimize updating only specific parts of the actual DOM.  
- 이 함수 호출은 JSX를 React의 자체적인 가벼운 DOM 표현으로 삽입하는 역할을 합니다. 그런 다음 React는 자체 DOM의 스냅샷을 사용하여 실제 DOM의 특정 부분만 업데이트하는 최적화 작업을 수행합니다.
- React는 JSX 코드를 내부적으로 자체적인 가벼운 DOM 표현으로 변환한 다음, 이를 사용하여 실제 웹 페이지의 DOM(Document Object Model)을 효율적으로 업데이트하여 성능을 최적화합니다. 이렇게 함으로써 React는 웹 페이지나 애플리케이션의 성능을 향상시킬 수 있습니다."
***

`ReactDOM.render(JSX, document.getElementById('root'))`에서 두 개의 인수는 다음과 같은 역할을 합니다:

- **JSX**: 이 첫 번째 인수는 React 엘리먼트나 JSX 코드를 나타냅니다. 이것은 화면에 렌더링하고자 하는 컴포넌트 또는 JSX 구조를 의미합니다. React는 이 JSX 코드를 가상 DOM(Virtual DOM)으로 변환하여 화면에 표시하고 실제 DOM을 업데이트하는 데 사용합니다.
- **document.getElementById('root')**: 이 두 번째 인수는 렌더링된 컴포넌트를 실제로 표시할 HTML 요소를 지정합니다. 이 부분은 웹 페이지의 HTML 구조에서 id가 'root'인 요소를 찾아서 해당 위치에 JSX 또는 React 엘리먼트를 렌더링합니다. 이것이 React 앱이 브라우저의 특정 DOM 요소에 렌더링되는 위치를 가리키며, React는 이 곳에 컴포넌트를 삽입하고 업데이트합니다.

***

For instance, because JSX is a syntactic extension of JavaScript, you can actually write JavaScript directly within JSX. To do this, you simply include the code you want to be treated as JavaScript within curly braces: `{ 'this is treated as JavaScript code' }`.  
- 이 문장은 JSX가 JavaScript의 구문 확장(Syntactic extension)이기 때문에 JSX 내에서 직접 JavaScript 코드를 작성할 수 있다는 내용을 설명하고 있습니다. JSX 내에서 JavaScript 코드를 사용하려면 중괄호 `{}` 안에 JavaScript 코드를 포함하면 됩니다. 중괄호 내부에 있는 코드는 JavaScript로 처리됩니다.  

```jsx
const myVar = 10;

const MyComponent = () => {
  return (
    <div>
      <p>The value of myVar is: {myVar}</p>
    </div>
  );
}
```
위의 코드에서 `{myVar}` 부분은 중괄호로 둘러싸인 JavaScript 코드입니다. 이 코드는 JSX 내에서 JavaScript 변수 `myVar`의 값을 출력합니다. JSX 내에서 중괄호를 사용하여 JavaScript 코드를 삽입하면 JSX와 JavaScript를 혼합하여 사용할 수 있으며, 이것은 React 컴포넌트에서 동적인 데이터를 표시하는 데 매우 유용합니다.

***

```jsx
const JSX = <div></div>;
```
The current code uses JSX to assign a `div` element to the constant `JSX`. Replace the `div` with an `h1` element and add the text `Hello JSX!` inside it.  
```jsx
const JSX = <h1>Hello JSX!</h1>;
```

## Create a Complex JSX Element

The last challenge was a simple example of JSX, but JSX can represent more complex HTML as well.
One important thing to know about nested JSX is that it must return a single element.
This one parent element would wrap all of the other levels of nested elements.
For instance, several JSX elements written as siblings with no parent wrapper element will not transpile.

Here's an example:  

**Valid JSX:**
```jsx
<div>
  <p>Paragraph One</p>
  <p>Paragraph Two</p>
  <p>Paragraph Three</p>
</div>
```

**Invalid JSX:**
```jsx
<p>Paragraph One</p>
<p>Paragraph Two</p>
<p>Paragraph Three</p>
```

***

Define a new constant `JSX` that renders a `div` which contains the following elements in order:

An `h1`, a `p`, and an unordered list that contains three `li` items. You can include any text you want within each element.

**Note**: When rendering multiple elements like this, you can wrap them all in parentheses, but it's not strictly required. Also notice this challenge uses a `div` tag to wrap all the child elements within a single parent element. If you remove the `div`, the JSX will no longer transpile. Keep this in mind, since it will also apply when you return JSX elements in React components.
- React 컴포넌트에서 JSX를 반환할 때 모든 JSX 요소는 단일 부모 요소로 감싸져야 합니다. 일반적으로 <div> 또는 <Fragment>(React 16 이상에서 사용 가능) 등을 사용하여 모든 자식 요소를 래핑합니다.

***

괄호로 묶는 것 예시
```jsx
const MyComponent = () => {
  return (
    <div>
      <h1>Hello</h1>
      <p>This is a paragraph.</p>
    </div>
  );
}
```
괄호로 묶지 않는 것 예시
```jsx
const MyComponent = () => {
  return <div>
    <h1>Hello</h1>
    <p>This is a paragraph.</p>
  </div>;
}
```
- 괄호를 사용하면 코드를 더 읽기 쉽게 만들고, 요소가 어디에서 시작하고 끝나는지를 명확하게 보여줍니다. 코드가 복잡해지면 괄호의 사용은 더 중요해질 수 있으며, 중첩된 JSX 구조에서 특히 유용합니다.

***

```jsx
const JSX = <div>
  <h1></h1>
  <p></p>
  <ul>
    <li></li>
    <li></li>
    <li></li>
  </ul>
</div>;
```

## Add Comments in JSX

JSX is a syntax that gets compiled into valid JavaScript. Sometimes, for readability, you might need to add comments to your code. Like most programming languages, JSX has its own way to do this.

To put comments inside JSX, you use the syntax `{/* */}` to wrap around the comment text.

***

The code editor has a JSX element similar to what you created in the last challenge. Add a comment somewhere within the provided `div` element, without modifying the existing `h1` or `p` elements.
```jsx
const JSX = (
  <div>
    {/* 안녕 */}
    <h1>This is a block of JSX</h1>
    <p>Here's a subtitle</p>
  </div>
);
```

## Render HTML Elements to the DOM

o far, you've learned that JSX is a convenient tool to write readable HTML within JavaScript. With React, we can render this JSX directly to the HTML DOM using React's rendering API known as ReactDOM.

ReactDOM offers a simple method to render React elements to the DOM which looks like this: `ReactDOM.render(componentToRender, targetNode)`, where the first argument is the React element or component that you want to render, and the second argument is the DOM node that you want to render the component to.

As you would expect, `ReactDOM.render()` must be called after the JSX element declarations, just like how you must declare variables before using them.  

***

The code editor has a simple JSX component. Use the `ReactDOM.render()` method to render this component to the page. You can pass defined JSX elements directly in as the first argument and use `document.getElementById()` to select the DOM node to render them to. There is a `div` with `id='challenge-node'` available for you to use. Make sure you don't change the JSX constant.  

```jsx
const JSX = (
  <div>
    <h1>Hello World</h1>
    <p>Lets render this to the DOM</p>
  </div>
);
// Add your code below this line

ReactDOM.render(JSX, document.getElementById('challenge-node'));
```

## Define an HTML Class in JSX

Now that you're getting comfortable writing JSX, you may be wondering how it differs from HTML.

So far, it may seem that HTML and JSX are exactly the same.

One key difference in JSX is that you can no longer use the word `class` to define HTML classes. This is because `class` is a reserved word in JavaScript. Instead, JSX uses `className`.

In fact, the naming convention for all HTML attributes and event references in JSX become camelCase. For example, a click event in JSX is `onClick`, instead of `onclick`. Likewise, `onchange` becomes `onChange`. While this is a subtle difference, it is an important one to keep in mind moving forward.

***

Apply a class of `myDiv` to the `div` provided in the JSX code.

```jsx
const JSX = (
  <div className="myDiv">
    <h1>Add a class to this div</h1>
  </div>
);
```

## Learn About Self-Closing JSX Tags

So far, you’ve seen how JSX differs from HTML in a key way with the use of `className` vs. `class` for defining HTML classes.

Another important way in which JSX differs from HTML is in the idea of the self-closing tag.

In HTML, almost all tags have both an opening and closing tag: `<div></div>`; the closing tag always has a **forward** slash before the tag name that you are closing. However, there are special instances in HTML called “self-closing tags”, or tags that don’t require both an opening and closing tag before another tag can start.

For example the line-break tag can be written as `<br>` or as `<br />`, but should never be written as `<br></br>`, *since it doesn't contain any content.*

In JSX, the rules are a little different. Any JSX element can be written with a self-closing tag, and every element ***must be closed.*** The line-break tag, for example, must always be written as `<br />` in order to be valid JSX that can be transpiled. A `<div>`, on the other hand, can be written as `<div />` or `<div></div>`. The difference is that in the first syntax version there is no way to include anything in the `<div />`. You will see in later challenges that this syntax is useful when rendering React components.

***

```jsx
const JSX = (
  <div>
    <h2>Welcome to React!</h2> <br >
    <p>Be sure to close all tags!</p>
    <hr >
  </div>
);
```
Fix the errors in the code editor so that it is valid JSX and successfully transpiles. Make sure you don't change any of the content - you only need to close tags where they are needed.

```jsx
const JSX = (
  <div>
    <h2>Welcome to React!</h2> <br />
    <p>Be sure to close all tags!</p>
    <hr />
  </div>
);
```

## Create a Stateless Functional Component

Components are the core of React. Everything in React is a component and here you will learn how to create one.

There are two ways to create a React component. The first way is to use a JavaScript function. Defining a component in this way creates a stateless functional component. The concept of state in an application will be covered in later challenges. For now, think of a stateless component as one that can receive data and render it, but does not manage or track changes to that data. (We'll cover the second way to create a React component in the next challenge.)

To create a component with a function, you simply write a JavaScript function that returns either JSX or `null`. One important thing to note is that React requires your function name to begin with a **capital letter**. Here's an example of a stateless functional component that assigns an HTML class in JSX:
```jsx
const DemoComponent = function() {
  return (
    <div className='customClass' />
  );
};
```
After being transpiled, the `<div>` will have a CSS class of `customClass`.

Because a JSX component represents HTML, you could put several components together to create a more complex HTML page. This is one of the key advantages of the component architecture React provides. It allows you to compose your UI from many separate, isolated components. This makes it easier to build and maintain complex user interfaces.

***

The code editor has a function called `MyComponent`. Complete this function so it returns a single `div` element which contains some string of text.

**Note**: The text is considered a child of the `div` element, so you will not be able to use a self-closing tag.

```jsx
const MyComponent = function() {
  // Change code below this line
  return (
    <div>Hello!</div>
  )
  // Change code above this line
}
```

## Create a React Component

The other way to define a React component is with the ES6 `class` syntax. In the following example, `Kitten` extends `React.Component`:
```jsx
class Kitten extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <h1>Hi</h1>
    );
  }
}
```
This creates an ES6 class `Kitten` which extends the `React.Component` class. So the `Kitten` class now has access to many useful React features, such as local state and lifecycle hooks. Don't worry if you aren't familiar with these terms yet, they will be covered in greater detail in later challenges. Also notice the `Kitten` class has a `constructor` defined within it that calls `super()`. It uses `super()` to call the constructor of the parent class, in this case `React.Component`. The constructor is a special method used during the initialization of objects that are created with the `class` keyword. It is best practice to call a component's `constructor` with `super`, and pass `props` to both. This makes sure the component is initialized properly. For now, know that it is standard for this code to be included. Soon you will see other uses for the constructor as well as `props`.

***

`MyComponent` is defined in the code editor using class syntax. Finish writing the `render` method so it returns a `div` element that contains an `h1` with the text `Hello React!`.

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    // Change code below this line
    return (
      <div>
        <h1>Hello React!</h1>
      </div>
    );
    // Change code above this line
  }
};
```

