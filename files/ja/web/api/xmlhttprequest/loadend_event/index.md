---
title: 'XMLHttpRequest: loadend イベント'
slug: Web/API/XMLHttpRequest/loadend_event
tags:
  - API
  - イベント
  - NeedsCompatTable
  - NeedsSpecTable
  - ProgressEvent
  - リファレンス
  - ウェブ
  - イベント
  - loadend
browser-compat: api.XMLHttpRequest.loadend_event
translation_of: Web/API/XMLHttpRequest/loadend_event
---
{{APIRef}}

**`loadend`** イベントは、リクエストが完了したときに、成功した場合 ({{domxref("XMLHttpRequest/load_event", "load")}} の後)、成功しなかった場合 ({{domxref("XMLHttpRequest/abort_event", "abort")}} または {{domxref("XMLHttpRequest/error_event", "error")}} の後) のどちらでも発行されます。

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">バブリング</th>
      <td>なし</td>
    </tr>
    <tr>
      <th scope="row">キャンセル</th>
      <td>不可</td>
    </tr>
    <tr>
      <th scope="row">インターフェイス</th>
      <td>{{domxref("ProgressEvent")}}</td>
    </tr>
    <tr>
      <th scope="row">イベントハンドラープロパティ</th>
      <td><code>onloadend</code></td>
    </tr>
  </tbody>
</table>

## 例

### ライブデモ

#### HTML

```html
<div class="controls">
    <input class="xhr success" type="button" name="xhr" value="Click to start XHR (success)" />
    <input class="xhr error" type="button" name="xhr" value="Click to start XHR (error)" />
    <input class="xhr abort" type="button" name="xhr" value="Click to start XHR (abort)" />
</div>

<textarea readonly class="event-log"></textarea>
```

```css hidden
.event-log {
    width: 25rem;
    height: 4rem;
    border: 1px solid black;
    margin: .5rem;
    padding: .2rem;
}

input {
    width: 11rem;
    margin: .5rem;
}
```

#### JS

```js
const xhrButtonSuccess = document.querySelector('.xhr.success');
const xhrButtonError = document.querySelector('.xhr.error');
const xhrButtonAbort = document.querySelector('.xhr.abort');
const log = document.querySelector('.event-log');

function handleEvent(e) {
    log.textContent = log.textContent + `${e.type}: ${e.loaded} bytes transferred\n`;
}

function addListeners(xhr) {
    xhr.addEventListener('loadstart', handleEvent);
    xhr.addEventListener('load', handleEvent);
    xhr.addEventListener('loadend', handleEvent);
    xhr.addEventListener('progress', handleEvent);
    xhr.addEventListener('error', handleEvent);
    xhr.addEventListener('abort', handleEvent);
}

function runXHR(url) {
    log.textContent = '';

    const xhr = new XMLHttpRequest();
    addListeners(xhr);
    xhr.open("GET", url);
    xhr.send();
    return xhr;
}

xhrButtonSuccess.addEventListener('click', () => {
    runXHR('https://raw.githubusercontent.com/mdn/content/main/files/en-us/_wikihistory.json');
});

xhrButtonError.addEventListener('click', () => {
    runXHR('http://i-dont-exist');
});

xhrButtonAbort.addEventListener('click', () => {
    runXHR('https://raw.githubusercontent.com/mdn/content/main/files/en-us/_wikihistory.json').abort();
});
```

#### 結果

{{ EmbedLiveSample('Live_example', '100%', '150px') }}

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- 関連イベント: {{domxref("XMLHttpRequest/loadstart_event", "loadstart")}}, {{domxref("XMLHttpRequest/load_event", "load")}}, {{domxref("XMLHttpRequest/progress_event", "progress")}}, {{domxref("XMLHttpRequest/error_event", "error")}}, {{domxref("XMLHttpRequest/abort_event", "abort")}}
- [進捗の監視](/ja/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest#monitoring_progress)
