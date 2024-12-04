# CSS 3

CSS - Cascading Style Sheets: sử dụng để định kiểu (style) cho các tài liệu HTML

### 1. History

- 1994: Håkon Wium Lie đề xuất ý tưởng về CSS khi đang làm việc tại CERN (tổ chức nghiên cứu hạt nhân châu Âu) nơi khai sinh ra World Wide Web.
- 1996: CSS1 được W3C giới thiệu như một khuyến nghị chính thức. CSS1 hỗ trợ các tính năng cơ bản như màu sắc, phông chữ và khoảng cách giữa các phần tử
- 1998: CSS2 ra đời, bổ xung nhiều tính năng mới + Hỗ trợ các phương tiện khác nhau (media types) như màn hình, máy in + positioning và z-index + table và các giao diện phức tạp
  => Dù CSS2 có nhiều cải tiến nhưng việc hỗ trợ của trình duyệt thời đó (như Internet Explore, Netscape) không nhất quán gây ra nhiều khó khăn.
- 2001: CSS3 ra đời. W3C bắt đầu làm việc trên CSS3
  - CSS3 được chia thành nhiều module (module-based)
  - Mội module phát triển độc lập giúp triển khai nhanh hơn
  - Selectors: hỗ trợ bộ chọn nâng cao (pseudo-classes, pseudo-elements)
  - Border-radius: Hiệu ứng bo góc
  - Box-shadow: Đổ bóng
  - Gradient: Dải màu
  - Multiple backgrounds: Hỗ trợ ảnh nền đa lớp
  - Media Queries: Tích hợp responsive giúp website tương thích với nhiều thiết bị khách nhau
  - Transitons, animations và transformations: Cho phép update các hoạt ảnh và chuyển đổi.
- 2020: Không có CSS4 chính thức mà chỉ có các module CSS được phát triển:
  - CSS Variables: Cho phép sử dụng biến trong CSS
  - Grid layout và Flexbox: giải pháp mạnh mẽ cho việc xây dựng layout
  - Subgrid: Một số tính năng mở rông của Grid Layout
  - Container Queries: Hỗ trợ thiết kế dựa trên kích thước container thay vì kích thước toàn màn hình

### 2. CSS 3 và các update

#### Selectors

Tăng cường khả năng chọn phần từ giảm phụ thuộc vào Javascript

- :nth-child(), :nth-last-child(), :nth-of-type(): Chọn phần tử dựa trên vị trí
- :not(): Chọn phần tử không hớp với một selector cụ thể
- :checked, :disabled, :enabled: Pseudo-classes cho form
- ::before, ::after: tách biệt hoàn toàn với :after, :before của CSS2

#### Box Model

- box-sizing: Cho phép tính toán kích thước phần tử dựa trên context-box hoặc border-box
- overflow-x, overflow-y: Điều khiển tràn nội dung theo trục cụ thể

#### Background và borders

- border-radius: Tạo góc bo tròn cho viền
- box-shadow: Đổ bóng cho phần tử
- background-size: Kiểm soát kích thước ảnh nền
- background-origin, background-clip: Điều chỉnh vùng ảnh nền
- Hỗ trợ nhiều ảnh nền: background:url(img1), url(img2)

#### Text Effects

- text-shadow: Tạo bóng cho văn bản
- word-wrap: Điều chỉnh cách từ ngắt dòng
- text-overflow: Hiển thị dấu chấm lửng khi văn bản tràn (ellipsis)
- white-space: Cải tiến cách xử lý khoảng trắng

#### Fonts

- Web Fonts: Hỗ trợ nhúng phông chữ tùy chỉnh bằng @font-face
- Các định dạng phông chữ hỗ trợ: TTF, OTF, WOFF, WOFF2
- font-variant, font-stretch: Thêm thuộc tính cải thiện việc kiểm soát kiểu chữ

#### Colors

Hỗ trợ các giá trị màu RGBA và HSLA

- RGBA: Thêm giá trị alpha cho độ trong suốt
- HSLA: Màu sắc dựa trên hệ thống Hue, Saturation, Lightness và Alpha

#### Transitions và Animations

- Transition: Tạo hiệu ứng chuyển đổi trạng thái như transition-property, transition-duration, transition-timing-function, transition-delay
- Animations: Sử dụng @keyframes để định nghĩa animation
- Thêm các thuộc tính quan trọng: animation-name, animation-duration, animation-timing-function, animation-interation-count, animation-direction

#### 2D/3D Transformations

- Transform 2D: translate(), rotate(), scale(), skew()
- Transform 3D: rotateX(), rotateY(), perspective(), thêm chiều sâu vào thiết kế web

#### Flexible Box Layout (Flexbox)

- Căn chỉnh phần tử theo trục ngang (row) hoặc dọc (column)
- Thuộc tính chính: display:flex, flex-direction, justify-content, align-items, flex-wrap, aligh-self

#### Grid Layout

- Cải tiến vượt trội về layout
- Các thuộc tính chính: display:grid, grid-template-rows, grid-template-columns, grid-gap, grid-area.

#### Media Queries

Cho phép thay đổi giao điện dựa trên kích thước hoặc loại thiết bị

```css
@media (max-width: 768px) {
  body {
    background-color: lightblue;
  }
}
```

#### Multi-column Layout

Tạo văn bản bằng nhiều cột
Các thuộc tính: column-count, column-gap, column-rule

#### Filter Effects

Các bộ lọc như blur, brightness, contrast, grayscale, sepia

#### Custom Properties (CSS Variables)

Cho phép sử dụng biến trong CSS

```css
:root {
  --main-color: #3498db;
}
body {
  color: var(--main-color);
}
```

#### Cải tiến khác

- Clipping và Masking: clip-path: Tạo vùng hiển thị tùy chỉnh cho phần tử
- mask: Thêm hiệu ứng mặt nạ cho phần tử
- overflow: scroll, hidden
