# Định nghĩa Component trong ReactJs

Component trong ReactJs là :

- đơn vị độc lập của code có thể được `tái sử dụng(reusable)`
- được sử dụng để `xây dựng giao diện người dùng (UI)`
- `quản lý trạng thái` hiển thị
- `xử lý các tương tác từ người dùng`
- giúp chia nhỏ code để gọn gàng hơn `(code splitting)`.

# Hướng dẫn sử dụng

Trong ReactJs có hai loại component chính là `Class Component` và `Functional Component`.

## Class Component

- Có thể sử dụng các tính năng như `state, lifecycle methods và refs`
- Phải kế thừa từ lớp `React.Component` hoặc `React.PureComponent`
- Được viết dưới dạng `class` và có thể được khởi tạo với các `props` khác nhau
- Không trực tiếp` return JSX`, mà thay vào đó render() method được sử dụng để trả lại `JSX`.
- Thường được sử dụng cho các component lớn, phức tạp hơn vì chúng có nhiều logic xử lý và nhiều trạng thái state khác nhau.

Ví dụ:

```JSX
import React, {Component} from "react";

class Counter extends Component {
    constructor(props) {
        super(props);
        this.state = {
            count: 0
        }; // initialize state object here if needed (e.g., for counters
    }

    handleOnClick = () => {
        this.setState({count: this.state.count + 1});
    }

    render() {
        return (
            <div>
                <p>You clicked {this.state.count} times.</p>
                <button onClick={() => this.handleOnClick()}>Click me</button>
            </div>
        );
    }
}

export default Counter;
```

Trong ví dụ trên, chúng ta định nghĩa một class component `Counter` để hiển thị số lần click vào button. Component này có hai phương thức `constructor()` và `render()`, cùng với một phương thức `handleClick()`.

- `constructor()` được gọi khi component được khởi tạo và được sử dụng để thiết lập `state` ban đầu cho component. Trong ví dụ trên, `state` bao gồm một thuộc tính count có giá trị ban đầu là 0.

- `handleClick()` được sử dụng để cập nhật giá trị của state khi button được click. Khi phương thức này được gọi, chúng ta sử dụng phương thức `setState()` để cập nhật giá trị của thuộc tính count.

- `render()` được sử dụng để hiển thị giao diện người dùng của component. Trong ví dụ trên, chúng ta sử dụng state để hiển thị số lần click vào button và cập nhật giá trị của s`tate khi button được click.

- Lưu ý: không cần sử dụng từ khóa `function` để định nghĩa phương thức trong class component. Thay vào đó, chúng ta có thể định nghĩa các phương thức bằng cách sử dụng cú pháp `methodName() {}`.

## Functional Component

- Không thể sử dụng các tính năng như state và lifecycle methods. Tuy nhiên, từ phiên bản ReactJS 16.8, functional component cũng có thể giải quyết vấn đề bằng cách sử dụng `Hook`.
- Là một function, không cần kế thừa bất kỳ class nào của React.
- Nhận vào các props và trả lại JSX
- Tính đơn giản và hiệu quả hơn so với class components
- Thường được sử dụng cho các component nhỏ, đơn giản, không có quá nhiều logic xử lý để xây dựng.

Ví dụ:

```JSX
import React from 'react';

function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}

export default Welcome;
```

Hoặc arrow function:

```JSX
const Welcome = (props) => {
    return <h1>Hello, {props.name}!</h1>;
}

export default ComponentA
```
