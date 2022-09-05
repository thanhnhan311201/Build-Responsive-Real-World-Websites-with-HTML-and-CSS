##### Table of content

- [Lý thuyết cơ bản về Layout và CSS Grid](#lý-thuyết-cơ-bản-về-layout-và-css-grid)
  - [Layout là gì?](#layout-là-gì)
  - [Các loại Layout](#các-loại-layout)
  - [Các cách để xây dựng bố cục với CSS](#các-cách-để-xây-dựng-bố-cục-với-css)
    - [Float Layout](#float-layout)
      - [Float Layout là gì?](#float-layout-là-gì)
      - [Thuộc tính _clear_](#thuộc-tính-clear)
      - [Khắc phục hiện tượng thẻ cha thu gọn chiều cao](#khắc-phục-hiện-tượng-thẻ-cha-thu-gọn-chiều-cao)
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

#### Float Layout là gì?

- **Float layout** là bố cục đầu tiên được áp dụng cho hầu hết tất cả các website, đây là một bố cục khá cũ và nó được nhanh chóng thay thế bởi các bố cục hiện đại hơn sau này. Tuy nhiên ngày nay vẫn còn một số website vẫn còn áp dụng kiểu bố cục như thế này.
- Ta biết rằng từ "float" có nghĩa là "nổi". Một trang HTML thông thường được trình bày theo dạng flow, tức là giống như một văn bản vậy, từng đoạn 1 xếp chồng lên nhau, cái nào viết trước nằm ở trên. Tuy nhiên, khi thiết kế bố cục website, có những phần tử không chỉ phân bố theo chiều dọc, mà còn theo chiều ngang, như ví dụ trên. Thuộc tính Float ra đời vì mục đích đó.
- **Float layout** là bố cục được xây dựng bằng cách sử dụng thuộc tính _float_ của CSS. Thuộc tính Float có 5 giá trị: none, left, right, initial và inherit. Trong đó, giá trị left và right được sử dụng nhiều nhất.
- Khi một phần tử nào đó được áp dụng thuộc tính _float_, nó nổi lên trên so với trang HTML (coi như nó tàng hình vậy). Lúc này, trang HTML sẽ coi như phần tử này không hề tồn tại, và chuyển các phần tử khác thế chỗ nó hoặc là làm cho các phần tử khác "nổi" xung quanh phần tử đó.
- **Lưu ý**:
  - Các phần tử _float_ chỉ có thể được bố trí theo phương ngang (trái hoặc phải) chứ không thể được bố trí theo phương dọc.
  - Tương tự như thuộc tính position _absolute_, các phần tử được áp dụng thuộc tính _float_ sẽ nổi lên trên HTML (out of flow). Tuy nhiên các phần tử xung quanh vẫn sẽ bị tác động và "nổi" xung quanh phần tử _float_, còn phần tử được áp dụng thuộc tính position "absolute" sẽ không làm tác động được các phần tử xung quanh.
  - Một lưu ý quan trọng là thẻ cha chứa các phần tử _float_ sẽ không tự điều chỉnh chiều cao cho các phần tử đó, bởi vì các phần tử _float_ lúc này sẽ _out of flow_ nên không còn thuộc trong thẻ cha đó, nên sẽ xảy ra hiện tượng thẻ cha thu gọn chiều cao và không còn chứa các phần tử _float_.
- Ví dụ:

Trước khi áp dụng thuộc tính _float_:

![](/Screenshots/non-float.png)

Sau khi áp dụng thuộc tính _float left_ cho thẻ img:

![](/Screenshots/float.png)

#### Thuộc tính _clear_

- Thuộc tính _clear_ là thuộc tính được dùng khi ta muốn xóa đi ảnh hưởng của thuộc tính _float_, cụ thể là xóa đi ảnh hưởng của phần tử ngay trước phần tử ta áp dụng thuộc tính _clear_.
- Thuộc tính _clear_ có 3 giá trị chính: left, right và both. Trong đó, ta hầu như dùng giá trị both xuyên suốt quá trình thiết kế.
- Chúng ta thường sử dụng thuộc tính _clear_ trong trường hợp khi chúng không muốn phần tử phía sau bị ảnh hưởng tới thuộc tính float. Ví dụ khi chúng ta có một trang html bao gồm 2 thẻ img và thẻ div chứa nội dung, trong đó thẻ img đã được _float left_ nên thẻ div chứa nội dung ở sau bị đây lên trên và đứng phía bên phải thẻ img (như hình bên dưới):

![](/Screenshots/non-clear-example-code.png)

![](/Screenshots/float.png)

Giả sử bây giờ chúng ta muốn đẩy thẻ div nội dung xuống dưới để không nằm bên phải thẻ img nữa thì chúng ta phải làm sao?

- Để có thể đẩy thẻ div nội dung xuống dưới thẻ img thì chúng ta có thể bỏ thuộc tính _float left_ của thẻ img đi, thì lúc này thẻ img sẽ nằm trong **normal flow** nên sẽ được bố trí theo thứ tự trước sau (thẻ img trước sẽ nằm trên, thẻ div nằm dưới).
- Ngoài ra chúng ta có thể sử dụng thuộc tính _clear_ cho thẻ div nhằm xóa bỏ đi sự ảnh hưởng thuộc tính _float_ của thẻ img trước đó, sau khi áp dụng thuộc tính _clear_ cho thẻ div chúng ta cũng sẽ có kết quả tương tự:

![](/Screenshots/clear-example-code.png)

![](/Screenshots/clear-example.png)

#### Khắc phục hiện tượng thẻ cha thu gọn chiều cao

- Trong phần lưu ý ở **Float Layout**, chúng ta đã biết thẻ cha sẽ không tự điều chính chiều cao cho các phần tử con được áp dụng thuộc tính _float_, điều đó sẽ xảy ra hiện tượng thu gọn chiều cao và không còn chứa các phần tử chứa bên trong đó (như hình bên dưới):

![](/Screenshots/collapse-height-with-float.png)

Trong thẻ header có chứa 2 thẻ con là h1 và nav, tuy nhiên 2 phần tử con này đã được áp dụng thuộc tính _float_, cho nên lúc này thẻ header đã thu gọn chiều cao và không còn chứa 2 thẻ h1 và nav, chiều cao lúc này còn lại là nhờ thuộc tính _padding_ (như bỏ thuộc tính _padding_ thì thẻ header lúc này sẽ biến mất)

- Chúng ta sẽ khắc phục trường hợp đó bằng cách tạo một thẻ div rỗng ngay sau thẻ h1 và thẻ nav, và áp dụng cho thẻ div rỗng đó thuộc tính _clear_. Lúc này thẻ div rỗng đó sẽ không bị ảnh hưởng bởi thuộc tính _float_ của 2 thẻ h1 và nav trước đó, và nó nằm ở dưới 2 thẻ đó.
- Code:

![](/Screenshots/fix-collapse-height-code-1.png)

- Vì thẻ header vẫn còn chứa thẻ div rỗng (thẻ div rỗng không có áp dụng thuộc tính _float_) nên vẫn sẽ tự động điều chỉnh chiều cao để chứa thẻ div rỗng, và vì thẻ div rỗng nằm ở dưới 2 thẻ h1 và nav nên thẻ header sẽ vô tình chứa cả 2 thẻ đó.
- Kết quả:

![](/Screenshots/fix-collapse-height.png)

- Tuy nhiên với cách như trên chúng ta sẽ làm cho file html bị lộn xộn không được gọn gàng với nhiều thẻ div rỗng (trong trường hợp có nhiều thẻ cha bị thu gọn chiều cao), để tránh việc tạo thẻ div rỗng chúng ta có thể sử dụng một thủ thuật sử dụng thuộc tính _clear_ với **pseudo-elements** được gọi là _clearfix_.
- _clearfix_ là thủ thuật được sử dụng khá phổ biến trong cộng đông CSS.
- Ý tưởng của thủ thuật cũng tương tư như cách chúng ta thêm một thẻ div rỗng vào ngay sau các phần tử _float_, tuy nhiên chúng ta sẽ sử dụng **pseudo-elemet after** để thêm một phần tử con ở cuối thay vì phải thêm thẻ div rỗng.
- Cách áp dụng:

![](/Screenshots/fix-collapse-height-code-2-html.png)

```
.clearfix::after {
  content: "";
  display: block;

  clear: both;
}
```

- Kết quả:

![](/Screenshots/fix-collapse-height.png)

### Flexbox layout

- **Flexbox layout** là bố cục mà nó sẽ tự cân đối kích thước của các phần tử bên trong để hiển thị trên một webpage.
- **Flexbox layout** được sử dụng để sắp xếp các phần tử trên cùng một chiều (có thể chiều ngang hoặc chiều dọc) mà không cần cho nó thuộc tính _float_.
- **Flexbox layout** sẽ thích hợp khi chúng ta cần xây dựng **component layout** hoặc các bố cục đơn giản trong phạm vi nhỏ (những khung trong website), còn khi chúng ta cần xây dựng các bố cục phức tạp hơn như chia cột website thì chúng ta nên sử dụng **Grid layout**.
- Để có thể sử dụng được kiểu bố cục **flexbox** chúng ta sẽ sử dụng thuộc tính _flexbox_ trong CSS.

### CSS Grid layout

- **Grid layout** là một bố cục hiện đại được sử dụng khá phổ biến ngày nay.
- **Grid layout** được sử dụng để sắp xếp các phần tử theo dạng lưới 2 chiều, với **Grid layout** các phần tử được chia thành các cột và hàng nhằm tạo ra một bố cục nhất quán và liền mạch trên website.
- **Grid layout** sẽ thích hợp khi chúng ta cần xây dựng **big page layout** hoặc các bố cục phức tạp như chia các cột website.
