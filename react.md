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

For instance, because JSX is a syntactic extension of JavaScript, you can actually write JavaScript directly within JSX. To do this, you simply include the code you want to be treated as JavaScript within curly braces: { 'this is treated as JavaScript code' }. Keep this in mind, since it's used in several future challenges.

However, because JSX is not valid JavaScript, JSX code must be compiled into JavaScript. The transpiler Babel is a popular tool for this process. For your convenience, it's already added behind the scenes for these challenges. If you happen to write syntactically invalid JSX, you will see the first test in these challenges fail.

It's worth noting that under the hood the challenges are calling ReactDOM.render(JSX, document.getElementById('root')). This function call is what places your JSX into React's own lightweight representation of the DOM. React then uses snapshots of its own DOM to optimize updating only specific parts of the actual DOM.
