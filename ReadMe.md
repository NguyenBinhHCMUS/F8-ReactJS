## Bài 1: ReactJS là gì?

ReactJS là thự viện JS để xay dựng giao diện người dùng.
React.js là một mã nguồn mở được phát triền bởi Facebook vào năm 2011. Nó được xây dựng dựa trên nguyên lý Component-based Approach, để có thể dễ dàng tái sử dụng, nhất là đối với các Single Page Application
## Bài 2: SPA/MPA

### SPA – Single-Page Application (kiến trúc phía dưới)
  * ReactJS là 1 trong những thư viện tạo ra SPA
  * Các ông lớn sử dụng SPA: GG, FB, TW
  * Các SPA khác: F8, Shopee, 30Shine, chotot, zingmp3

### Cách triển khai
  * SPA: lần đẩu tải về root trống, sau đó thực thi JS để tạo ra các DOM element để thêm vào root element.
  * MPA: trả về đầy đủ HTML.

### Sự khác biệt


# Bài 8: document.createElement()

Là phương thức của document object dùng để tạo ra DOM element.

  1. document.createElement()
  2. document.body.appendChild()
  3. console.dir()
  4. innerText, id, className, style

```html
<body>

  <div id="root"></div>

  <script>
    const root = document.getElementById('root');
    const h1 = document.createElement('h1');

    h1.innerHTML = "Bai 8";

    h1.id = 'heading';

    h1.className = 'heading';

    h1.style.color = 'red';
    h1.style = 'color: green; font-size: 5rem;'

    root.appendChild(h1);

    console.log(h1);
  </script>
</body>
```

# Bài 9 Cách thêm React vào Website

```html
<script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>
```

# Bài 10 React.createElement()
1. React.createElement() -> React element.
2. So sánh với document.createElement() -> DOM element.
3. Thay đổi id, className, style,..
4. Thêm: text, HTML.
5. BT

``` React.createElement(type, props, children);```

Children cũng là props.

Tạo

```html
<!-- <h1 title="Hello" class="heading">Hello guys!</h1> -->
<script>
  // DOM
  const root = document.getElementById('root');
  const h1Dom = document.createElement('h1');
  h1Dom.title = "Hello";
  h1Dom.className = "heading";
  h1Dom.innerHTML = "Hello guys!";

  console.log(h1Dom);

  root.appendChild(h1Dom);

  // React
  const h1React = React.createElement('h1', {
    title: 'Hello',
    className: 'heading'
  }, 'Hello guys!');

  console.log(h1React);

</script>
```
Tạo:
```html
<!--
    <ul>
      <li>Javascript</li>
      <li>ReactJS</li>
    </ul>
-->
  <script>
    const root = document.getElementById('root');
    // DOM
    const ulDom = document.createElement('ul');
    const li1Dom = document.createElement('li');
    li1Dom.innerText = 'Javascript';
    const li2Dom = document.createElement('li');
    li2Dom.innerText = 'ReactJS';

    ulDom.appendChild(li1Dom);
    ulDom.appendChild(li2Dom);
    root.appendChild(ulDom);

    // React
    const ulReact = React.createElement(
      'ul',
      null,
      React.createElement('li', { style: 'color:red;' }, 'JavaScript'),
      React.createElement('li', null, 'ReactJS')
    )
    console.log(ulReact);

  </script>
```
Tạo:
```html
<!--
  <div class="post-item">
    <h2 title="Học React tại F8">Học ReactJS</h2>
    <p>Học ReactJS từ cơ bản đến nâng cao.</p>
  </div>
-->
<script>
    // DOM
    const root = document.getElementById('root')
    const divDom = document.createElement('div')
    divDom.className = 'post-item'

    const h2Dom = document.createElement('h2')
    h2Dom.title = 'Học React tại F8'
    h2Dom.innerText = 'Học ReactJS'

    const pDom = document.createElement('p')
    pDom.innerText = 'Học ReactJS từ cơ bản đến nâng cao.'

    divDom.appendChild(h2Dom)
    divDom.appendChild(pDom)
    root.appendChild(divDom)

    // React
    const divReact = React.createElement(
      'div',
      {
        className: 'post-item'
      },
      React.createElement('h2', { title: 'Học React tại F8' }, 'Học ReactJS'),
      React.createElement('p', null, 'Học ReactJS từ cơ bản đến nâng cao.')
    )
    console.log(divReact)

  </script>
```

# Bài 11 React-DOM là gì? Tại sao cần React-DOM?

- React-DOM: là thư viện cầu nối giữa React và DOM.
- Tạo sao phải sử dụng React-DOM: render react element ra giao diện người dùng.
- Tại sao lại tách React-DOM ra: để phân biệt (React-DOM, React-Native) là những cầu nối từ react ==> Không thuộc thư viện React.
- RenderUI.

```js
// React-DOM --> renderUI
// render(element, container, callback)
ReactDOM.render(divReact, root)
```
# Bài 12 JSX là gì? Tại sao cần JSX?


