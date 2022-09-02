##### Table of content

- [Lý thuyết cơ bản về Layout và CSS Grid](#lý-thuyết-cơ-bản-về-layout-và-css-grid)
  - [Layout là gì?](#layout-là-gì)
  - [Các loại Layout](#các-loại-layout)
  - [Các cách để xây dựng bố cục với CSS](#các-cách-để-xây-dựng-bố-cục-với-css)
    - [Float Layout](#float-layout)
    - [Flexbox layout](#flexbox-layout)
    - [CSS Grid layout](#css-grid-layout)

# Lý thuyết cơ bản về Layout và CSS Grid

## Layout là gì?

- Trong thiết kế và phát triển web, _layout web_ được hiểu là cách bố trí, thiết kế, sắp xếp các nội dung văn bản, hình ảnh và tất cả các nội dung khác trên một website.
- **Layout web** sẽ giúp cho website có một cấu trúc trực quan, từ cấu trúc trực quan đó chúng ta có thể dễ dàng sắp xếp các nội dung cũng như các phần tử trên một website.
- **Building a layout** hay còn gọi _xây dựng bố cục_ là việc chúng ta sắp xếp các thành phần của website vào một cấu trúc trực quan nào đó, thay vì chúng ta trình bày các phần tử của website theo trình tự nối tiếp nhau từ trên xuống dưới (normal flow). Với việc thiết kế bố cục sẽ giúp cho website trở nên sinh động và trực quan hơn, và dễ dàng trong việc truyền tải nội dung cũng như ý tưởng của website đến người dùng hơn.

  Trang web thiết kế không có bố cục:

  ![](/Screenshots/normal-flow-web.png)

  Trang web thiết kế có bố cục:

  ![](/Screenshots/architecture-design-website.png)

## Các loại Layout

- Trong một website, chúng ta sẽ có 2 loại layout căn bản: **page layout** và **component layout**.
- **Page layout** là cách sắp xếp các thành phần chính, các phần nội dung lớn bên trong một webpage hay một website.
- Các thành phần chính (element) trong một webpage được cấu tạo từ các thành phần nhỏ hơn (component), và các component này sẽ được cấu tạo từ nhiều nội dung nhỏ bên trong (content). Do đó để website trở nên sinh động thì các nội dung nhỏ bên trong component cũng cần sắp xếp theo một bố cục nào đó, bố cục đó được gọi là **component layout**.
- Tương tự, bên trong các component lớn cũng được cấu tạo từ các component nhỏ hơn, và các component nhỏ này cũng cần được thiết kế theo một **component layout** nào đó.

Phân biệt giữa **page layout** và **component layout**:
![](/Screenshots/page-%26-component-layout.png)

## Các cách để xây dựng bố cục với CSS

Trong thiết kế một webpage, chúng ta có 3 cách để xây dựng bố cục với CSS: **float layout**, **flexbox layout**, **CSS grid layout**.

![](/Screenshots/layouts.png)

### Float Layout

- **Float layout** là bố cục đầu tiên được áp dụng cho hầu hết tất cả các website, đây là một bố cục khá cũ và nó được nhanh chóng thay thế bởi các bố cục hiện đại hơn sau này. Tuy nhiên ngày nay vẫn còn một số website vẫn còn áp dụng kiểu bố cục như thế này.
- **Float layout** là bố cục được xây dựng bằng cách sử dụng thuộc tính _float_ của CSS.
- Với thuộc tính _float_, các phần tử có thể được bố trí về phía bên trái hoặc phía bên phải. Với các phần tử khi được cùng bố trí về một phía thì các phần tử sẽ nối đuôi nhau.
- Một điều lưu ý là các phần tử _float_ chỉ có thể được bố trí theo phương ngang (trái hoặc phải) chứ không thể được bố trí theo phương dọc.

### Flexbox layout

- **Flexbox layout** là bố cục mà nó sẽ tự cân đối kích thước của các phần tử bên trong để hiển thị trên một webpage.
- **Flexbox layout** được sử dụng để sắp xếp các phần tử trên cùng một chiều (có thể chiều ngang hoặc chiều dọc) mà không cần cho nó thuộc tính _float_.
- **Flexbox layout** sẽ thích hợp khi chúng ta cần xây dựng **component layout** hoặc các bố cục đơn giản trong phạm vi nhỏ (những khung trong website), còn khi chúng ta cần xây dựng các bố cục phức tạp hơn như chia cột website thì chúng ta nên sử dụng **Grid layout**.
- Để có thể sử dụng được kiểu bố cục **flexbox** chúng ta sẽ sử dụng thuộc tính _flexbox_ trong CSS.

### CSS Grid layout

- **Grid layout** là một bố cục hiện đại được sử dụng khá phổ biến ngày nay.
- **Grid layout** được sử dụng để sắp xếp các phần tử theo dạng lưới 2 chiều, với **Grid layout** các phần tử được chia thành các cột và hàng nhằm tạo ra một bố cục nhất quán và liền mạch trên website.
- **Grid layout** sẽ thích hợp khi chúng ta cần xây dựng **big page layout** hoặc các bố cục phức tạp như chia các cột website.
