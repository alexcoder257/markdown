# Eloquent Javascript

## Function

#### Keywords:

- Parameters
- Arguments
- Global scope
- Local scope
- Lexical scoping
- Function declaration
- Function expression
- Arrow function
- Call stack
- Optional Arguments
- Closure
- Recursion

## Higher-Order functions

Functions that operate on other functions, either by taking them as arguments or by returning them, are called higher-order functions

#### Keywords:

- Map
- Filter
- Reduce
- Foreach
- Some
- Every
- Sort

#### Array method

- Map

```javascript
const numbers = [1, 2, 3, 4];
const squared = numbers.map((num) => num ** 2);
console.log(squared); // [1, 4, 9, 16]
```

- Filter

```javascript
const numbers = [1, 2, 3, 4];
const evenNumbers = numbers.filter((num) => num % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

- Reduce

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum); // 10
```

- For each

```javascript
const numbers = [1, 2, 3, 4];
numbers.forEach((num) => console.log(num * 2));
// Output: 2, 4, 6, 8
```

- Some

```javascript
const numbers = [1, 2, 3, 4];
const hasEven = numbers.some((num) => num % 2 === 0);
console.log(hasEven); // true
```

- Every

```javascript
const numbers = [2, 4, 6, 8];
const allEven = numbers.every((num) => num % 2 === 0);
console.log(allEven); // true
```

- Sort

```javascript
const numbers = [3, 1, 4, 2];
const sorted = numbers.sort((a, b) => a - b);
console.log(sorted); // [1, 2, 3, 4]
```

- Custom Higher-Order functions

```javascript
function multiplyBy(num) {
  return function (value) {
    return value * num;
  };
}
const double = multiplyBy(2);
console.log(double(5)); // 10
```

```javascript
function createLogger(prefix) {
  return function (message) {
    console.log(`[${prefix}] ${message}`);
  };
}
const infoLogger = createLogger("INFO");
infoLogger("This is a log message"); // [INFO] This is a log message
```

## Modules

- ES modules
- ECMAScript 2015
- Packages
- CommonJS modules
- Bundlers

## Asynchronous Programming

- Synchronous
- Asynchronous
- Thread
- Callbacks
- Promises
- Event loop

## Javascript and the brower

#### Keywords:

- Internet
- Network protocol
- Hyper Text Transfer Protocol - HTTP
- Transmission Control Protocol - TCP
- Port
- World wide web - www
- IP address
- Domain name
- HyperText Markup Language - HTML

## Handling Events

#### Keywords:

- Real DOM
- Virtual DOM
- Propagation
- Pointer events
- Scroll events
- Focus events
- Load event

#### Events

##### Mouse Events

- click: Khi người dùng nhấp chuột trái vào một phần tử.
- dblclick: Khi người dùng nhấp đúp chuột.
- mousedown: Khi nhấn chuột (chưa nhả ra).
- mouseup: Khi nhả chuột sau khi nhấn.
- mousemove: Khi chuột di chuyển qua một phần tử.
- mouseover: Khi chuột di chuyển vào bên trong phần tử.
- mouseout: Khi chuột rời khỏi phần tử.
- contextmenu: Khi nhấp chuột phải để mở menu ngữ cảnh.

```javascript
document.querySelector("button").addEventListener("click", () => {
  alert("Button clicked!");
});
```

##### Keyboard Events

- keydown: Khi nhấn một phím (chưa nhả).
- keyup: Khi nhả phím ra.
- keypress (đã deprecated): Khi nhấn một phím ký tự.

```javascript
document.addEventListener("keydown", (event) => {
  console.log(`Phím bạn nhấn: ${event.key}`);
});
```

#### Form Events

- submit: Khi gửi biểu mẫu (form).
- change: Khi giá trị trong một phần tử form thay đổi.
- input: Khi người dùng nhập dữ liệu vào một phần tử.
- focus: Khi phần tử được focus.
- blur: Khi phần tử mất focus.
- reset: Khi form được reset.

```javascript
document.querySelector("form").addEventListener("submit", (event) => {
  event.preventDefault(); // Ngăn chặn hành động mặc định
  alert("Form submitted!");
});
```

#### Window Events

- load: Khi toàn bộ trang (bao gồm hình ảnh, script) được tải xong.
- DOMContentLoaded: Khi DOM đã được tải xong, không cần đợi hình ảnh/script.
- resize: Khi kích thước cửa sổ thay đổi.
- scroll: Khi người dùng cuộn trang.
- unload: Khi người dùng thoát khỏi trang.

```javascript
window.addEventListener("resize", () => {
  console.log(
    `Chiều rộng: ${window.innerWidth}, Chiều cao: ${window.innerHeight}`
  );
});
```

#### Element Events

- change: Khi giá trị của phần tử input, select, textarea thay đổi.
- select: Khi văn bản được chọn trong input hoặc textarea.
- focus và blur: Khi phần tử nhận hoặc mất tiêu điểm.

```javascript
const input = document.querySelector("input");
input.addEventListener("focus", () => {
  console.log("Input được focus!");
});
input.addEventListener("blur", () => {
  console.log("Input mất focus!");
});
```

#### Drag and Drop Events

- dragstart: Khi bắt đầu kéo một phần tử.
- drag: Khi đang kéo.
- dragend: Khi dừng kéo.
- dragenter: Khi kéo vào một phần tử hợp lệ.
- dragover: Khi giữ phần tử kéo qua một khu vực.
- dragleave: Khi rời khỏi phần tử hợp lệ.
- drop: Khi thả phần tử.

```javascript
const draggable = document.querySelector(".draggable");
draggable.addEventListener("dragstart", () => {
  console.log("Bắt đầu kéo!");
});
```

#### Media Events

- play: Khi media bắt đầu phát.
- pause: Khi media bị tạm dừng.
- ended: Khi phát media đến cuối.
- volumechange: Khi thay đổi âm lượng.
- timeupdate: Khi thời gian phát media thay đổi.

```javascript
const video = document.querySelector("video");
video.addEventListener("play", () => {
  console.log("Video đang phát!");
});
```
