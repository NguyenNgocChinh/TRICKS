# Tự động load lại position được lưu

Lưu position scroll vào session storage.

Trước khi load trang sẽ kiểm tra session storage và scroll xuống.

Nhớ đặt nó vào trong ready jquery.

## Code

Dán đoạn code này vào trong file js.
```bash

    $(window).scroll(function () {
        sessionStorage.scrollTop = $(this).scrollTop();
    });

    $(document).ready(function () {
        if (sessionStorage.scrollTop != "undefined") {
            $(window).scrollTop(sessionStorage.scrollTop);
        }

    });

```

## Auto load lại position với các trang riêng lẻ
Dán đoạn code này vào trong file js.
```bash

    $(window).scroll(function () {
        sessionStorage.scrollTop = $(this).scrollTop();
        sessionStorage.currentPage = document.location.protocol +"//"+ document.location.hostname + document.location.pathname;
    });

    $(document).ready(function () {
        if (sessionStorage.scrollTop != "undefined") {
            let current_url = document.location.protocol +"//"+ document.location.hostname + document.location.pathname;
            if (current_url == sessionStorage.currentPage) {
                $(window).scrollTop(sessionStorage.scrollTop);
            }
        }

    });

```

Chúc các bạn code may mắn.