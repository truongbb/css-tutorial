# 1. CSS Combinators
## 1.1. CSS Combinators - Bộ kết hợp CSS
- Bộ chọn CSS có thể chứa nhiều hơn 1 bộ chọn đơn (selector). Giữa các bộ chọn đơn, chúng ta có thể bao gồm 1 bộ kết hợp.
- Bộ kết hợp sẽ hiểu đơn giản là  mối quan hệ giữa các bộ chọn đơn.
- Có 4 bộ chọn kết hợp khác nhau trong CSS:
    - `Descendant selector (space)`
    - `Child selector (>)`
    - `Adjacent sibling selector (+)`
    - `General sibling selector (~)`
`
### 1.1.1. Descendant Selector
- Bộ chọn `Descendant Selector` có nghĩa là `chọn tất cả những thẻ nằm trong một selector nào đó`. Cú pháp sử dụng dấu cách (space) giữa 2 phần tử `Element Element {}`   
VD: chọn tất cả các thẻ `<p>` nằm trong thẻ `<div>`
    <p align="center">
    <img src="../images/lesson2/descendant_selector.png" width=500>
    </p>
### 1.1.2. Child selector (>)
- `Child selector (>)` có ý nghĩa là `chọn tất cả những thẻ con trực tiếp của một selector` nào đó. Nghĩa là thẻ con nằm trong đúng một cấp so với selector đó.
- Cú pháp : `element > element {}`  
VD: Chọn tất cả thẻ con `<p>` cấp 1 nằm trong thẻ `<div>`
    <p align="center">
    <img src="../images/lesson2/child_selector.png" width=500>
    </p>

    - Thẻ `<p>` chứa nội dung "Paragraph 3 in the div" không được chọn vì nó là thẻ con cấp 1 của thẻ `<section>` hay gọi là thẻ cháu của thẻ `<div>`

### 1.1.3 Adjacent sibling selector (+)
- `Adjacent sibling selector (+)` có ý nghĩa là `chọn một thẻ anh/chị/em ruột nằm liền kề ngay sau một selector` nào đó.
- Thẻ anh/chị/em được hiểu là những thẻ có chung một thẻ cha.
- Cú pháp : `element + element {}`  
VD: Chọn thẻ `<p>` đầu tiên nằm ngay sau thẻ `<div>`

<p align="center">
<img src="../images/lesson2/adjacent_sibling.png" width=500>
</p>

### 1.1.4. General sibling selector (~)
- `General sibling selector (~)` có ý nghĩa là `chọn tất cả những thẻ anh/chị/em của 1 selector` nào đó. Tuy nhiên những thẻ này `phải nằm phía sau selector` đó.
- Cú pháp : `element ~ element {}`    
VD: 
    <p align="center">
    <img src="../images/lesson2/general_sibling.png" width=500>
    </p>

# 2. CSS Pseudo-Classes
## 2.1. Pseudo-Classes là gì?
- `Pseudo-class (Một lớp giả)` được sử dụng để xác định trạng thái đặc biệt của một phần tử.
- Ví dụ, nó có thể được sử dụng để:
    - Tạo kiểu cho một phần tử khi người dùng di chuột qua nó.
    - Tạo kiểu cho các liên kết được truy cập và không được truy cập một cách khác nhau...

- Cú pháp:

```css
selector:pseudo-class {
    property: value;
}
```
## 2.2. Anchor Pseudo-classes
- Các liên kết có thể được hiển thị theo các cách khác nhau.
VD:
```css
/* unvisited link */
a:link {
  color: red; /*Khi liên kết chưa được truy cập thì có màu đỏ*/
}

/* visited link */
a:visited {
  color: green; /*Khi liên kết được truy cập rồi thì có màu xanh lá*/
}

/* mouse over link */
a:hover {
  color: yellow; /*Khi di chuột qua liên kết thì có màu vàng*/
}

/* selected link */
a:active {
  color: blue; /*Khi liên kết được click thì có màu xanh dương*/
}
```
## 2.3. Pseudo-classes and HTML Classes
- Có thể kết hợp `Pseudo-class` với tên class của HTML.

VD: Thay đổi màu sắc của thẻ liên kết `<a>` có `class="highlight"` khi di chuột vào liên kết đó.
```css
a.highlight:hover {
  color: #ff0000;
  font-size: 22px;
} 
```

## 2.4. Di chuột qua một phần tử để hiển thị lên một phần tử khác (giống như hiển thị 1 công cụ giải thích)  

VD: khi di chuột vào thẻ `<div>` thì thẻ `<p>` được hiển thị ra
    <p align="center">
    <img src="../images/lesson2/tooltip_hover.png" width=500>
    </p>
## 2.5. CSS - The :first-child Pseudo-class
- `:first-child pseudo-class` sẽ chọn một phần tử mà phần tử đó là thẻ con đầu tiên của 1 phần tử khác  
- VD:
    - Chọn phần tử `<p>` bất kỳ là phần tử con đầu tiên của 1 phần tử khác.
    <p align="center">
    <img src="../images/lesson2/first_child.png" width=500>
    </p>

    - Chỉ có phần tử chứa nội dung "This is p1." và "This is p3." được chọn vì p1 là phần tử con đầu tiên của phần tử `<body>`, p3 là phần tử con đầu tiên của phần tử `<div>`

VD: 
-  Chọn phần tử con `<i>` đầu tiên trong tất cả các phần tử `<p>`
    <p align="center">
    <img src="../images/lesson2/i_first_child.png" width=500>
    </p>

VD:
- Chọn tất cả phần tử con `<i>` nằm trong phần tử `<p>` mà phần tử `<p>` đó lại là phần tử con đầu tiên của một phần tử nào đó.
    <p align="center">
    <img src="../images/lesson2/all_i_first_child.png" width=500>
    </p>

## 2.6. CSS - The :lang Pseudo-class
- `:lang pseudo-class` cho phép ta xác định các quy tắc đặc biệt cho các ngôn ngữ khác nhau.  
VD:
 `:lang` xác định dấu ngã (~) cho các phần tử `<q>` với `lang = "no"`:
    <p align="center">
    <img src="../images/lesson2/lang_pseudo.png" width=500>
    </p>

# 3. CSS Pseudo-elements
- Một CSS `pseudo-element` thường được sử dụng để định kiểu cho các thành phần cụ thể của một phần tử.  
VD: nó có thể được sử dụng để:
    - Định kiểu cho ký tự, dòng hay của một phần tử đầu tiên.
    - Chèn nội dung vào trước hoặc sau một nội dung của một phần tử.

- Cú pháp: 
```css
selector::pseudo-element {
  property: value;
}
```
## 3.1. The ::first-line Pseudo-element
- `::firstline Pseudo-element` được sử dụng để thêm một định kiểu đặc biệt tới dòng đầu tiên của một văn bản.  
VD: định dạng cho dòng đầu tiên của văn bản trong tất cả các thẻ `<p>`
    <p align="center">
    <img src="../images/lesson2/first_pseudo_element.png" width=500>
    </p>

*lưu ý:* `::first-line pseudo-element` chỉ có thể áp dụng cho những phần tử mức khối
- Một số thuộc tính áp dụng cho `::first-line pseudo-element`:
    - Thuộc tính `font`, `color`, `background`
    - `word-spacing`
    - `letter-spacing`
    - `text-decoration`
    - `vertical-align`
    - `text-transform`
    - `line-height`
    - `clear`

**Chú ý ::first-line  với :first-line**
- Hai dấu hai chấm (`::`) được thay thế cho 1 dấu hai chấm (`:`) phía trước một `pseudo-element trong CSS3`. Và điều này là để phân biệt giữa `pseudo-classes là 1 dấu (:)` và `pseudo-elements là 2 dấu (::)`.
- Đối với `CSS2` và `CSS1` thì cú pháp sủ dụng `1 dấu hai chấm (:) được sử dụng cho cả pseudo-classes và pseudo-elements`

## 3.2. The ::first-letter Pseudo-elements
- `::first-letter pseudo-element` được sử dụng để thêm một định kiểu đặc biệt tới ký tự đầu tiên của một văn bản.

VD: định kiểu cho ký tự đầu tiên của văn bản trong tất cả thẻ `<p>`
    <p align="center">
    <img src="../images/lesson2/first_letter_pseudo_element.png" width=500>
    </p>

*Lưu ý:* `::first-letter pseudo-element` chỉ có thể áp dụng cho những phần tử mức khối
- Một số thuộc tính áp dụng cho `::first-letter pseudo-element`:
    - Thuộc tính `font`, `color`, `background`
    - `margin`, `padding`, `border`
    - `text-decoration`
    - `vertical-align` (chỉ có giá trị float là không áp dụng)
    - `text-transform`
    - `line-height`
    - `float`
    - `clear`
## 3.3. Kết hợp Pseudo-elements và HTML Classes
- `Pseudo-elements` có thể được kết hợp với HTML `class` theo cú pháp:
```css
    selector.class::pseudo-element  {
        property: value;
    }
```
VD:
    <p align="center">
    <img src="../images/lesson2/pseudo_element_class.png" width=500>
    </p>

## 3.4. Multiple Pseudo-elemnts
- Một vài `pseudo-elements` cũng có thể được kết hợp với nhau:  
VD: Kết hợp `::first-letter` và `::first-line` của `pseudo-elements` cho một đoạn văn bản.   

<p align="center">
<img src="../images/lesson2/pseudo_element_combination.png" width=500>
</p>
    
## 3.5. CSS ::before, ::after Pseudo-element
- `::before`/`::after Pseudo-element` có thể được sử dụng để chèn một số nội dung vào trước/sau nội dung có trong một phần tử.  
- Cú pháp:
```css
selector::before {
    content: "add content";
}

selector::after {
    content: "add content";
}
```
VD: 
- Chèn một hình ảnh vào trước nội dung của mỗi thẻ `<h1>`:
    <p align="center">
    <img src="../images/lesson2/before_pseudo.png" width=500>
    </p>

- Chèn một hình ảnh vào sau nội dung của mỗi thẻ `<h1>`:
    <p align="center">
    <img src="../images/lesson2/after_pseudo.png" width=500>
    </p>

## 3.6. CSS - The ::marker Pseudo-element
- CSS - `::marker Pseudo-element` chọn những điểm đánh dấu của các mục danh sách   
VD:
    <p align="center">
    <img src="../images/lesson2/makers_pseudo.png" width=500>
    </p>

## 3.6. CSS - The ::selection Pseudo-element
- `::selection Pseudo-element` dùng để định dạng cho những thành phần được người dùng chọn trong một phần tử.
- Những thuộc tính CSS được áp dụng cho `::selection`: `color, background, cursor, outline`.
VD: Những phần nào được chọn sẽ có chữ màu đỏ và màu nền là màu vàng
    <p align="center">
    <img src="../images/lesson2/select_pseudo.png" width=500>
    </p>

# 4. CSS Opacity/Transparency
- Thuộc tính opacity định nghĩa độ mờ/độ trong suốt của một phần tử.
## 4.1. Transparency Image
- Thuộc tính opacity có thể nhận 1 giá trị từ 0.0 - 1.0. Giá trị càng thấp thì càng mờ.  
VD:
    <p align = "center">
    <img width = 500 src="../images/lesson2/opacity.png">
    </p>

## 4.2. Transparent Hover Effect
- Thuộc tính opacity thường được sử dụng với bộ chọn :hover để thay đổi độ mờ khi di chuột qua một phần tử.
VD:
    <p align = "center">
    <img width = 500 src="../images/lesson2/hover_opacity.png">
    </p>

# 5. CSS Navigation Bar
## 5.1 Demo : Navigation Bar
- Navigation Bar = List of Links ( thanh điều hướng hay danh sách các liên kết)
- Một thanh điều hướng sử dụng những tiêu chuẩn HTML làm một cơ sở.
- Một thanh điều hướng cơ bản là một danh sách của các liên kết, vì vậy  sử dụng các phần tử <ul> và <li> để tạo danh sách.
VD:
    <p align = "center">
    <img width = 500 src="../images/lesson2/hover_opacity.png">
    </p>
Lưu ý: sử dụng thuộc tính href="#" trong thẻ `<a>` cho các liên kết thực nghiệm. Trong một trang web thực, đây sẽ là một URLs