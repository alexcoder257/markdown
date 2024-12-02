# React

### 1. Lịch sử phát triển React

- 2011:
  Jordan Walke, một kỹ sư tại Facebook, đã phát triển một nguyên mẫu ban đầu của React, được gọi là FaxJS.Giúp xây dựng UI bằng cách sử dụng virtual DOM
- 2012:
  React sử dụng để làm trang News feed của facebook
- 2013:
  Facebook chính thức ra mắt react tại hội nghị Javascript. React trở thành mã nguồn mở trên Github
- 2016:
  React đạt phiên bản 15.0 đạt cải tiến về hiệu năng, API và JSX trở thành một phần quan trọng trong hệ sinh thái React
- 2018:
  React giới thiệu hook trong phiên bản 16.8. Một cuộc cách mạng hóa trong việc viết và quản lý state trong React.
- 2019:
  React Concurrent Mode và suspense được công bố mang lại khả năng tối ưu hóa hiệu năng cho ứng dụng phực tạp. React mở rộng thêm Redux, Next Js và nhiều thư viện liên quan
- 2022:
  React 18 với nhiều cải tiến lớn như Concurrent Rendering, Automatic Batching và các cái tiến về SSR

### 2. Hook vs Class trong React

#### Class

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0,
      userName: "",
      isLoggedIn: false,
    };
  }

  updateCounter = () => {
    this.setState({ counter: this.state.counter + 1 });
  };

  updateUserName = (name) => {
    this.setState({ userName: name }); // Có thể ghi đè các thuộc tính khác nếu không cẩn thận
  };

  toggleLogin = () => {
    this.setState((prevState) => ({ isLoggedIn: !prevState.isLoggedIn }));
  };

  render() {
    return (
      <div>
        <p>Counter: {this.state.counter}</p>
        <p>User: {this.state.userName}</p>
        <p>Logged in: {this.state.isLoggedIn ? "Yes" : "No"}</p>
        <button onClick={this.updateCounter}>Increment Counter</button>
        <button onClick={() => this.updateUserName("Alice")}>Set Name</button>
        <button onClick={this.toggleLogin}>Toggle Login</button>
      </div>
    );
  }
}
```

- Sử dụng cú pháp this.state hoặc setState để cập nhật lại state
- Sử dụng cú pháp this, dễ xảy ra lỗi khi xử lý trong các function
- Sử dụng cú pháp ES6 class
- Quản lý vòng đời qua các phương thức:
  - componentDidMount(): Được gọi sau khi component đã được gắn vào DOM.
  - shouldComponentUpdate(nextProps,nextState): Quyết định xem component có nên render lại hay không. Return true/false.
  - componentDidUpdate(): Được gọi sau khi DOM đã cập nhật. Dùng để thực hiện các tác vụ liên quan đến dữ liệu mới.
  - componentWillUnmount(): Được gọi trước khi component bị gỡ khỏi DOM. Dùng để clean up.

#### So sánh Lifecycle giữa Class và Hook

- Giống nhau:
  Đều xử lý 3 giai đoạn là : mount, update và unmount
- Khác nhau:
  Với Class: Mỗi vòng đời lại có một phương thức riêng tách biệt: + Mounting: constructor, componentDidMount. + Updating: shouldComponentUpdate, componentDidUpdate + Unmounting: componnetWillUnmount.
  => Cần nhớ và sử dụng đúng phương thức cho từng giai đoạn. Khó tái sử dụng và dễ gặp vấn để với logic phức tạp.
  Hook: Xử lý toàn bộ trong 1 hàm useEffect. Quản lý đơn giản qua dependency.

### 3. JSX convert to Javascript

- React sẽ cung cấp React.createElement để tạo nên các React Element - đơn vị nhỏ nhất trong React.
- Babel sẽ giúp chuyển đổi các đoạn mã JSX thành React.createElement. Ví dụ:

```javascript
const element = (
  <div className="container">
    <h1>Title</h1>
    <p>Description</p>
  </div>
);
```

Sẽ được Bable biên dịch thành:

```javascript
const element = React.createElement(
  "div",
  { className: "container" },
  React.createElement("h1", null, "Title"),
  React.createElement("p", null, "Description")
);
```

### 4. Virtual DOM

### 5. Code Splitting React.lazy và Suspense

### 6. Life circle

### 7. Hook

#### useCallback

#### useMemo

#### React.memo

#### useActionState

#### useContext

#### useDebugValue

#### useDeferredValue
