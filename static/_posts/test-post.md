---
layout: blog
title: Jam stack?
date: 2019-10-14T04:32:24.191Z
featured_image: /uploads/uhgkexe8lxjsmj6cznqmiw3bpsezn0mu9eun.png
description: Tại sao build blog bằng static site?
---
Ban đầu mình định  build blog này bằng [Wordpress](https://wordpress.com/) hoặc [React](https://reactjs.org/) - [Wordpress REST API](https://developer.wordpress.org/rest-api/) nhưng mình không tin tưởng perfomance sẽ cao và blog mình cũng thuộc dạng [static site](https://wsvincent.com/what-is-a-static-site-generator/) nên mình dùng [JAM stack](https://jamstack.wtf/) với [Svelte](https://svelte.dev/), [Sapper](https://sapper.svelte.dev/) và [Netlify](https://www.netlify.com/). Đại loại front-end sẽ dùng Svelte và Sapper để build bằng cách đọc file [Markdown](https://www.markdownguide.org/) ở local, render thành static site và host trên netlify. Tất cả source code đều nằm trên [github](https://github.com/nguyendq/sapper-netlify) và Netlify sẽ là nơi update content cũng như đọc change từ github để update lại. Pros and cons của stack nài sẽ như thế nào?

## Pros

1. Nhanh. File đã được compile và load thẳng thông qua CDN, không tương tác gì với database hết ráo.
2. Bảo mật. Do là file tĩnh nên khỏi lo về vấn đề SQL hay server side.
3. Rẻ. Cắt bớt 1 số phần backend tương đối.

## Cons

1. Khó phân quyền.
2. Dynamic elements. Giỏ hàng, form liên hệ...
3. Real time 

Tuy nhiên nếu dùng cho 1 blog siêu đơn giản thì vẫn ok, nên chọn
