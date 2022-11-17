# 🕸 Grid

## Lưu ý:

### `margin: auto` sẽ làm mất tác dụng của `grid-column`

Dưới đây là một element form có thuộc tính `grid-column`:&#x20;

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Class <code>.col-span-4</code> của TailwindCSS</p></figcaption></figure>

Thuộc tính này sẽ làm form hiển thị như sau:

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>Element tự động mở rộng theo chiều ngang để chiếm hết 4 cột của grid system</p></figcaption></figure>

Tuy nhiên nếu chúng ta thêm margin: auto <img src="../.gitbook/assets/image (2).png" alt="" data-size="original">

Margin sẽ tự lấy hết các khoảng trống phía bên ngoài và thu bé element lại vừa với nội dung bên trong

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>Element bị thu bé lại</p></figcaption></figure>
