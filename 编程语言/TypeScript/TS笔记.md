---
title: TS 笔记
tags:
  - TS
---

# TS实现重载

```ts
function message(options: object): void;
function message(text: string, onclose?: Function): void;
function message(text: string, mode: string, duration?: number): void;
function message(text: string, duration?: number, onClose?: Function): void;

function message(param1: string | Object, param2?: Function | string | number, param3?: Function | string | number): void {
  if (typeof param1 === 'string') {
  } else if (typeof param1 === 'object') {
  }
}
```

在对象里面实现承载

```ts
interface ShowMessage {
  (options: object): void;
  (text: string, onclose?: Function): void;
  (text: string, mode: string, duration?: number): void;
  (text: string, duration?: number, onClose?: Function): void;
}
interface Utils {
  showMessage: ShowMessage;
}

const utils: Utils = {
  showMessage(param1: string | Object, param2?: Function | string | number, param3?: Function | string | number) {}
};
```

