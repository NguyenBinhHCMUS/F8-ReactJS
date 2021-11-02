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

JSX --> Javascript XML

1. Luôn dùng React.createElement()? Vấn đề
2. JSX?
3. JSX không phải là HTML, cần có JS, Babel để dùng JSX
4. JSX và React-Dom

JSX để hỗ trợ viết html, xml trong file js.

Babel là thư viện JS chuyên dùng để phân tích và chuyển đổi cú pháp của JS > ES6 để trở thành ES5. Dùng để hổ trợ hầu hết các trình duyệt chạy JS.

```html
<script type="text/babel">
    // DOM
    const root = document.getElementById('root')

    const courses = [
      {
        name: 'HTML/CSS'
      },
      {
        name: 'Responsive web design'
      },
      {
        name: 'ReactJS'
      }
    ]


    // React
    const ul = <ul>
      {
        courses.map((course, index) => (
          <li key={index}>{course.name}</li>
        ))
      }
    </ul>

    // React-DOM --> renderUI
    // render(element, container, callback)
    ReactDOM.render(ul, root)

  </script>
```

# Bài 13 JSX render arrays

- Tại sao khi code thuần dùng map phải join() ==> chuyển đổi mảng thành chuổi để cho property innerHTML có thể nhận giá trị.
- Gặp lỗi khi render từ mảng {props "key"}
- Không render được 2 element cùng lúc ==> cần có thẻ ôm bên ngoài (div, React.Fragment)

# Bài 14 React element types

1. React element types: string, function/class
  - Wrapper
    - Header -> Header component
    - Content -> Content component
    - Footer -> Footer component
2. Biểu diễn đơn giản với JSX.

``` html
<script type="text/babel">
    const root = document.getElementById('root')

    function Header() {
      return (
        <div class="header">Header</div>
      )
    }

    class Content extends React.Component {
      render() {
        return (
          <div class="content">Content</div>
        )
      }
    }

    function PostItem() {
      return (
        <div class="post-item">
          <img src="https://cdn.fullstack.edu.vn/f8-learning/blog_posts/923/6169a3eaa8c07.png" alt="" />
          <h2 class="post-title">Life cycle của Component trong Reactjs</h2>
          <p class="post-desc">Chào anh Sơn và...</p>
          <p class="post-published">2 ngày trước * 3 phút đọc</p>
        </div>
      )
    }

    const app = (
      <div class="wrapper">
        <Header />
        <PostItem />
        <div class="footer">Footer</div>
      </div>
    )

    ReactDOM.render(app, root)
  </script>
```

  React element dùng làm function component có type là gì? ==> Function.

# Bài 15 Props là gì? Dùng props khi nào?

Props là object chứa thuộc tính để mô tả cho React Elemẹnt tạo ra.

- React elements
  - Sử dụng props giống như với attribute của thẻ HTML
  - 2 props class, for => className, htmlFor
  - Phải tuân theo qui ước có sẵn
- React components
  - Sử dụng props giống như đối số cho Component
  - Tự do đặt tên props
    - Đặt theo camelCase
    - Có thể bao gồm dấu gạch ngang
- Chú ý:
  - Props "key" là props đặc biệt, đưa react element/component vào trong array.
  - Props cơ bản là đối số của component => props có thể là bất cứ kiểu dữ liệu gì
  - Sử dụng destructuring

* Callback là 1 hàm được truyền thông qua đối số của hàm khác, truyền hàm qua props chính là hàm callback.

Bài tập: render ra danh sách khóa học trên F8

```html
 <script type="text/babel">
    const root = document.getElementById('root')

    // BT
    const courses = [
      {
        "id": 2,
        "category_id": 2,
        "title": "HTML, CSS từ Zero đến Hero",
        "slug": "html-css",
        "description": "Trong khóa này chúng ta sẽ cùng nhau xây dựng giao diện 2 trang web là The Band & Shopee.",
        "thumbnail": "courses/2.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "R6plN3FvzFY",
        "preview_path": null,
        "language": "html",
        "syntax_highligh": "language-html",
        "level": "Trình độ cơ bản",
        "priority": 10,
        "students_count": 62694,
        "created_at": "2020-04-10T14:23:13.000000Z",
        "updated_at": "2021-10-17T11:59:00.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/2.png"
      },
      {
        "id": 1,
        "category_id": 1,
        "title": "Javascript Cơ Bản",
        "slug": "javascript-co-ban",
        "description": "Học Javascript cơ bản phù hợp cho người chưa từng học lập trình. Với hơn 100 bài học và có bài tập thực hành sau mỗi bài học.",
        "thumbnail": "courses/1.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "0SJE9dYdpps",
        "preview_path": null,
        "language": "javascript",
        "syntax_highligh": "language-javascript",
        "level": "Trình độ cơ bản",
        "priority": 30,
        "students_count": 40605,
        "created_at": "2020-06-10T14:23:13.000000Z",
        "updated_at": "2021-10-17T11:59:29.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/1.png"
      },
      {
        "id": 7,
        "category_id": 4,
        "title": "Kiến Thức Nhập Môn",
        "slug": "lessons-for-newbie",
        "description": "Để có cái nhìn tổng quan về ngành IT - Lập trình web các bạn nên xem các videos tại khóa này trước nhé.",
        "thumbnail": "courses/7.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "M62l1xA5Eu8",
        "preview_path": null,
        "language": null,
        "syntax_highligh": null,
        "level": "Trình độ cơ bản",
        "priority": 0,
        "students_count": 34200,
        "created_at": "2020-02-10T14:23:13.000000Z",
        "updated_at": "2021-10-17T11:52:08.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/7.png"
      },
      {
        "id": 3,
        "category_id": 2,
        "title": "Responsive Với Grid System",
        "slug": "responsive-web-design",
        "description": "Trong khóa này chúng ta sẽ học về cách xây dựng giao diện web responsive với Grid System, tương tự Bootstrap 4.",
        "thumbnail": "courses/3.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "uz5LIP85J5Y",
        "preview_path": null,
        "language": "html",
        "syntax_highligh": "language-html",
        "level": "Trình độ cơ bản",
        "priority": 20,
        "students_count": 13853,
        "created_at": "2020-05-10T14:23:13.000000Z",
        "updated_at": "2021-10-17T11:18:23.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/3.png"
      },
      {
        "id": 6,
        "category_id": 3,
        "title": "Node & ExpressJS",
        "slug": "nodejs",
        "description": "Học Back-end với Node & ExpressJS framework, hiểu các khái niệm khi làm Back-end và xây dựng RESTful API cho trang web.",
        "thumbnail": "courses/6.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "z2f7RHgvddc",
        "preview_path": null,
        "language": "javascript",
        "syntax_highligh": "language-javascript",
        "level": "Trình độ cơ bản",
        "priority": 32,
        "students_count": 11733,
        "created_at": "2020-08-01T14:23:13.000000Z",
        "updated_at": "2021-10-17T11:44:53.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/6.png"
      },
      {
        "id": 5,
        "category_id": 2,
        "title": "HTML, CSS Tips & Tricks",
        "slug": "html-css-tutorials",
        "description": "Tutorials về HTML, CSS, UI, UX sẽ được tổng hợp tại khóa học này, các video có nội dung ngắn gọn, súc tích giúp học viên có thể ứng dụng ngay vào thực tế",
        "thumbnail": "courses/5.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "nB6cJh_bb1U",
        "preview_path": null,
        "language": "html",
        "syntax_highligh": "language-html",
        "level": "Trình độ cơ bản",
        "priority": 40,
        "students_count": 8840,
        "created_at": "2020-03-10T14:23:13.000000Z",
        "updated_at": "2021-10-17T11:54:47.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/5.png"
      },
      {
        "id": 12,
        "category_id": 1,
        "title": "Javascript Nâng Cao",
        "slug": "javascript-nang-cao",
        "description": "Hiểu sâu hơn về cách Javascript hoạt động, tìm hiểu về IIFE, closure, reference types, this keyword, bind, call, apply, prototype, ...",
        "thumbnail": "courses/12.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "MGhw6XliFgo",
        "preview_path": null,
        "language": "javascript",
        "syntax_highligh": "language-javascript",
        "level": "Trình độ nâng cao",
        "priority": 31,
        "students_count": 7233,
        "created_at": "2021-04-03T14:23:13.000000Z",
        "updated_at": "2021-10-17T10:04:19.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/12.png"
      },
      {
        "id": 13,
        "category_id": 0,
        "title": "ReactJS",
        "slug": "reactjs",
        "description": "Khóa học ReactJS từ cơ bản tới nâng cao, kết quả của khóa học này là bạn có thể làm hầu hết các dự án thường gặp với ReactJS. Cuối khóa học này bạn sẽ sở hữu một dự án giống Tiktok.com, bạn có thể tự tin đi xin việc khi nắm chắc các kiến thức được chia sẻ trong khóa học này.",
        "thumbnail": "courses/13/13.png",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "x0fSBAgBrOQ",
        "preview_path": null,
        "language": "javascript",
        "syntax_highligh": "language-jsx",
        "level": "Trình độ trung bình",
        "priority": 0,
        "students_count": 5488,
        "created_at": null,
        "updated_at": "2021-10-17T12:00:08.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/13/13.png"
      },
      {
        "id": 4,
        "category_id": 1,
        "title": "Don't Touch Your Face",
        "slug": "tool-canh-bao-so-len-mat",
        "description": "Xây dựng ứng dụng đưa ra cảnh báo khi người dùng sờ tay lên mặt. Chúng ta sẽ sử dụng thư viện ReactJS & Tensoflow để hoàn thiện ứng dụng này.",
        "thumbnail": "courses/4/4.jpeg",
        "content": null,
        "preview_origin": "youtube",
        "preview_youtube_id": "r6GWbQL-qwA",
        "preview_path": null,
        "language": "javascript",
        "syntax_highligh": "language-javascript",
        "level": "Trình độ cơ bản",
        "priority": 50,
        "students_count": 3338,
        "created_at": "2020-01-10T14:23:13.000000Z",
        "updated_at": "2021-10-17T10:13:30.000000Z",
        "thumbnail_cdn": "https://cdn.fullstack.edu.vn/f8-learning/courses/4/4.jpeg"
      }
    ]

    function CourseItem(props) {
      const { title, image, description, students_count } = props;
      return (
        <div className="course-item">
          <h2 className="title">{title}</h2>
          <img src={image} alt={title} />
          <p className="description">{description}</p>
          <p className="student-count">{students_count}</p>
        </div>
      )
    }

    // app.js
    function App() {
      return (
        <div id="wrapper">
          <PostItem
            title="Life cycle của Component trong Reactjs"
            image="https://cdn.fullstack.edu.vn/f8-learning/blog_posts/923/6169a3eaa8c07.png"
            description="Chào anh Sơn và..."
            published="2 ngày trước * 3 phút đọc"
          />

          <div class="courses">
            {
              courses.map((item, index) => (
                <CourseItem
                  key={index}
                  title={item.title}
                  image={item.thumbnail_cdn}
                  description={item.description}
                  students_count={item.students_count}
                />
              ))
            }
          </div>
        </div>
      )
    }
    // PostItem.js
    function PostItem(props) {
      const { title, image, description, published } = props;
      return (
        <div className="post-item">
          <img src={image} alt="" />
          <h2 className="post-title">{title}</h2>
          <p className="post-desc">{description}</p>
          <p className="post-published">{published}</p>
        </div>
      )
    }

    // index.js
    ReactDOM.render(<App />, root)


  </script>
```

# Bài 16 DOM events?

<!-- Phần I. -->
- Xử lý DOM events

Bài tập: alert ra tên khoá học

```js
// UI component
    function CourseItem(props) {
      const { title, image, description, studentCount, onClick } = props;
      return (
        <div className="course-item">
          <h2
            className="title"
            onClick={() => onClick(title)}
          >
            {title}
          </h2>
          <img src={image} alt={title} />
          <p className="description">{description}</p>
          <p className="student-count">{studentCount}</p>
        </div>
      )
    }

    // Container: dùng các UI component
    // app.js
    function App() {
      const handleClickTitle = (title) => alert(title);
      return (
        <div id="wrapper">

          <div className="courses">
            {
              courses.map((item, index) => (
                <CourseItem
                  key={index}
                  title={item.title}
                  image={item.thumbnail_cdn}
                  description={item.description}
                  studentCount={item.students_count}
                  onClick={handleClickTitle}
                />
              ))
            }
          </div>
        </div>
      )
    }
```

# Bài 17 Quy ước đặt tên components

- Component do chúng ta định nghĩa phải viết in hoa kí tự đầu tiên (thông qua obj có thể không cần, vẫn chạy không bị lỗi)
  - Chọn component trong 1 object
- Boolean, Null & undefined không được render
- Kết hợp toán tử logic để render theo điều kiện

Ghi chú:
- Bất cứ function nào cũng có thể làm function component
- Function trong object theo cách Enhance Object literal không cần từ "function"

```html
<script type="text/babel">
    const root = document.getElementById('root')

    const Form = {
      Input() {
        return <input />
      },
      Checkbox() {
        return <input type="checkbox" />
      }
    }

    function Button({ title, href, onClick }) {
      let Type = 'button';

      const props = {};

      if (href) {
        Type = 'a';
        props.href = href;
      }
      if (onClick) {
        // Type = 'button'
        props.onClick = onClick;
      }
      return (
        <Type {...props}>{title}</Type>
      )
    }

    // Container: dùng các UI component
    // app.js
    function App() {

      const type = 'Input';

      // Khi truyền Form[type] (nó là function cômponent)
      // vào jsx sẽ lỗi vì có ngoặc vuông
      const Component = Form[type];// sẽ không bị lỗi.

      let boolVar = true;

      return (
        <div id="wrapper">
          <Form.Input />
          <Form.Checkbox />
          <Component />

          <Button
            title="Click me"
            href="https://www.facebook.com/"
            onClick={() => console.log(Math.random())}
          />

          {true}
          {false}
          {undefined}

          {boolVar && <h1>Hello boolearn</h1>}

        </div>
      )
    }

    // index.js
    ReactDOM.render(<App />, root)


  </script>
```

# Bài 18 Children props? Render props?

<!-- Phần II. -->
- Props trong JSX
  - <NameComponent
      propName1="string literals"
      propName2={expression}
    />
  - Props default to 'true' (primary thay cho primary={true})
  - Spread/Rest props
  - Children props
    - <YourComponent>String literals</YourComponent>
    - <YourComponent>{expression}</YourComponent>
  - Render props

```html
<script type="text/babel">
    const root = document.getElementById('root')

    function Button({ title, primary }) {
      console.log(primary);

      return (
        <button>{title}</button>
      )
    }

    function Input({ label, ...inputProps }) {
      return (
        <React.Fragment>
          <label>{label}</label>
          <input {...inputProps} />
        </React.Fragment>
      )
    }

    function RenderPropsList(props) {
      return (
        <ul>
          {props.data.map(props.children)}
        </ul>
      )
    }

    // Container: dùng các UI component
    // app.js
    function App() {
      const title = "Hello";
      const cars = ['honda', 'yamaha'];
      return (
        <div>
          <Button
            primary
            title={title}
          />

          <Input
            label="name"
            type='checkbox'
          />

          <RenderPropsList data={cars}>
            {(item, index) => <li key={index}>{item}</li>}
          </RenderPropsList>
        </div>
      )

    }

    // index.js
    ReactDOM.render(<App />, root)
  </script>
```

# Bài 19 NodeJS là gì? Tại sao phải sử dụng NodeJS

NodeJS là javascript runtime tạo ra môi trường độc lập để thực thi code js (sử dụng Chrome's V8 Javascript engine - Google).

# Bài 20 Tạo dự án với React + Webpack

defer trong thẻ script chỉ tải file js về, sau khi chạy hết file html thì mới chạy code trong js.

# Bài 21 Create React App

Tạo dự án npx create-react-app ./

# Bài 22 NPM, NPX và YARN là gì?

1. NPX thực hiện tìm kiếm file `bin` của thư viện theo thứ tự nào? ==> Proeject scope, global scope, NPM
2. Giả sử trên máy tính của bạn đang cài đặt `create-react-app` ở phạm vi `global` thì khi chạy lệnh `npx create-react-app --help` điều gì sẽ xảy ra? ==> Nội dung help sẽ được in ra Terminal, create-react-app  ở phạm vi global được sử dụng.
3. Lệnh nào có thể sử dụng để cài đặt YARN? ==> npm i -g yarn.

# Bài 23 CRA Folder Structure

Các files trong thư mục `public` có thể truy cập qua đâu? Có thể truy cập công khai qua domain/IP web.

Mặc định web server được chạy khi `npm start` với CRA trỏ vào file nào? public/index.html

# Bài 24 Hooks là gì?

Bàn chất trong js thì hook là cái hàm, method được viết sẵn cung cấp bởi Reactjs dùng để gắn/móc vào function component. Mỗi hàm sẽ có 1 tính năng và trường hợp cụ thể để sử dụng.

Lợi ích:

- Khiến các component trở nên gọn nhẹ hơn
- Giảm đáng kể số lượng code, dễ tiếp cận
- Cho phép chúng ta sử dụng state ngay trong function component

```js
import {
    useState,
    useEffect,
    useLayoutEffect,
    useRef,
    useCallback,
    useMemo,
    useReducer,
    useContext,
    useImperativeHandle,
    useDegbugValue,
} from 'react';

// chua dung hooks, chi la UI component
function ComponentA() {
    return <h1>Haven't used hooks yet</h1>
}

// su dung hook, ho tro them nhieu tinh nang
function ComponentB() {
    // useState
    const [state, setState] = useState(initState)

    // useEffect
    useEffect(() => {

    }, [deps])

    // useLaytoutEffect
    useLayoutEffect(() => {

    }, [deps])

    // useRef
    const ref = useRef()

    // useCallback
    const fn = useCallback(() => {

    }, [deps])

    // useMemo
    const result = useMemo(() => {

    }, [deps])

    // useReducer
    const [state, dispatch] = useReducer(reducer, initialArg, init)

    // useContext
    const value = useContext(MyContext)

    // useImperativeHandle
    useImperativeHandle(ref, createHandle, [deps])

    // useDebugValue
    useDebugValue(isOnline ? 'Online' : 'Offline');

    return <h1>Hooks</h1>
}

```

1. Chỉ dùng cho function component
2. Component đơn giản và trở nên dễ hiểu
   - Không bị chia logic ra như methods trong lifecycle của Class Component
   - Không sử dụng 'this'
3. Sử dụng Hooks khi nào?
   - Dự án mới ==> hooks
   - Dự án cũ
     - Component mới ==> function component + hook
     - Component cũ ==> giữ nguyên, có thời gian tối ưu sau
   - Logic nghiệp vụ cần sử dụng các tính năng của OOP => Class component
4. Người mới nên bắt đầu Function component
5. Có kết hợp sự dụng Function component & Class component được không? ==> Được

# Bài 25. useState hook

### Dùng khi nào?
Khi muốn dữ liệu thay đổi khi giao diện tự động được cập nhật (render lại theo dũ liệu).

### Cách dùng
```jsx
import {useState} from 'react'

function Component() {
  const [state, setState] = useState[initialState]
}
```
### Lưu ý
- Component được re-render sau khi `setState`
- Initial state chỉ dùng cho lần đầu
- Set state với callback? ==> cho phép chạy nhiều setState trước khi re-render.
- Initial state với callback? ==> hàn chế cahỵ lại đoạn code khi re-render.
- Set state là thay thế state bằng giá trị mới.

# Bài 26. Two-way binding?

ReactJs: one-way binding ràng buộc 1 chiều.
- 1 chiều: là chiều tương tác với giao diện. Thay đổi giá trị ở giao diện thì dữ liệu (state) thay đổi.
- 2 là chiều dữ liệu: nếu có thể sửa dữ liệu trong component thì giao giện thay đổi theo.

Ứng dụng: đơn giản triển khai dữ liệu khi quản lý form.

```jsx
import React, { useState } from 'react';
import './App.css';

const gifts = [
  'CPU i9',
  'RAM 32GB RGB',
  'RGB Keyboard'
]

// Response from API
const courses = [
  {
    id: 1,
    name: 'HTML, Css'
  },
  {
    id: 2,
    name: 'JS'
  },
  {
    id: 3,
    name: 'Responsive'
  }
]
function App() {
  const [gift, setGift] = useState()
  const [name, setName] = useState('')
  const [user, setUser] = useState('')
  const [password, setPassword] = useState('')
  const [checked, setChecked] = useState()
  const [checkbox, setCheckbox] = useState([])

  const randomGift = () => {
    const index = Math.floor(Math.random() * gifts.length);
    setGift(gifts[index])
  }

  const formSubmit = () => {
    // Call API
    console.log({
      user,
      password
    })
  }

  const handleCheckedCheckbox = (id) => {
    setCheckbox(prev => {
      const isChecked = checkbox.includes(id)
      if (isChecked) {
        return checkbox.filter(item => item !== id)
      } else {
        return [...prev, id]
      }
    })
  }

  console.log(name)
  return (
    <div className="App" style={{ padding: 32 }}>
      <h1>{gift || 'Chưa có phần thưởng'}</h1>
      <button onClick={randomGift}>Lấy thưởng</button>

      <h1>Two-way binding</h1>
      <input
        value={name}
        onChange={(e) => setName(e.target.value)}
      />
      <button onClick={() => setName('Nguyen van tam binh')}>Change</button>

      <h2>Đăng ký</h2>
      <label>Username</label>
      <input
        value={user}
        onChange={e => setUser(e.target.value)}
      />

      <label>Password</label>
      <input
        type="password"
        value={password}
        onChange={e => setPassword(e.target.value)}
      />

      <button onClick={formSubmit}>Register</button>

      <h2>Checked</h2>
      {
        courses.map((item) => (
          <div key={item.id}>
            <input
              type='radio'
              checked={checked === item.id}
              onChange={() => setChecked(item.id)}
            />
            {item.name}
          </div>
        ))
      }
      <h2>Checkbox</h2>

      {
        courses.map((item) => (
          <div key={item.id}>
            <input
              type='checkbox'
              checked={checkbox.includes(item.id)}
              onChange={() => handleCheckedCheckbox(item.id)}
            />
            {item.name}
          </div>
        ))
      }
    </div>
  );
}

export default App;
```