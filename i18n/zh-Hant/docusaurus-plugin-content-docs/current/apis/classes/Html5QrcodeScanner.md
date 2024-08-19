---
sidebar_position: 2
---

[html5-qrcode](../) / Html5QrcodeScanner

# 類別：Html5QrcodeScanner

端到端的基於網頁的 QR 和條碼掃描器。

使用此類可以通過幾行程式碼在你的網頁應用程式中設定 QR 掃描器。

- 支援相機和檔案掃描。
- 根據裝置支援相機選擇、縮放和手電筒功能。
- 支援不同類型的 2D 和 1D 條碼 [Html5QrcodeSupportedFormats](../enums/Html5QrcodeSupportedFormats.md)。



## 目錄


### 建構函數

- [constructor](Html5QrcodeScanner.md#建構函數)

### Methods

- [applyVideoConstraints](Html5QrcodeScanner.md#applyvideoconstraints)
- [clear](Html5QrcodeScanner.md#clear)
- [getRunningTrackCapabilities](Html5QrcodeScanner.md#getrunningtrackcapabilities)
- [getRunningTrackSettings](Html5QrcodeScanner.md#getrunningtracksettings)
- [getState](Html5QrcodeScanner.md#getstate)
- [pause](Html5QrcodeScanner.md#pause)
- [render](Html5QrcodeScanner.md#render)
- [resume](Html5QrcodeScanner.md#resume)

## Constructors

### 建構函數

• **new Html5QrcodeScanner**(`elementId`, `config`, `verbose`)

創建這個類別的實例。

#### 參數

| 名稱 | 類型 | 描述 |
| :------ | :------ | :------ |
| `elementId` | `string` | HTML 元素的 ID。 |
| `config` | `undefined` \| `Html5QrcodeScannerConfig` | 調整程式碼掃描器的額外配置。 |
| `verbose` | `undefined` \| `boolean` | 如果為 true，所有日誌將輸出到 console。 |

#### 定義於

[html5-qrcode-scanner.ts:208](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L208)

## 方法

### applyVideoConstraints

▸ **applyVideoConstraints**(`videoConstraints`): `Promise`<`void`\>

對來自相機的執行視訊應用影片約束。

注意：僅當 [()](Html5QrcodeScanner.md#getstate) 返回 [SCANNING](../enums/Html5QrcodeScannerState.md#scanning) 或 [PAUSED](../enums/Html5QrcodeScannerState.md#paused) 時才應呼叫此方法。

**`Throws`**

如果掃描未處於執行狀態，則會拋出錯誤。

#### 參數

| Name | Type |
| :------ | :------ |
| `videoConstaints` | `MediaTrackConstraints` |

#### 回傳

`Promise`<`void`\>

一個 Promise，如果應用傳遞的約束成功則成功，否則失敗。
#### 定義於

[html5-qrcode-scanner.ts:428](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L428)

___

### clear

▸ **clear**(): `Promise`<`void`\>

移除 QR Code 掃描器 UI。

#### 回傳

`Promise`<`void`\>

成功完成清理則返回成功的 Promise，否則返回失敗的 Promise。

#### 定義於

[html5-qrcode-scanner.ts:335](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L335)

___

### getRunningTrackCapabilities

▸ **getRunningTrackCapabilities**(): `MediaTrackCapabilities`

傳回執行中的視訊軌道的功能
了解更多： https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints

Note: Should only be called if [()](Html5QrcodeScanner.md#getstate)
  returns [SCANNING](../enums/Html5QrcodeScannerState.md#scanning) or 
  [PAUSED](../enums/Html5QrcodeScannerState.md#paused).

**`Throws`**

如果掃描未處於運作狀態，則會出現錯誤。

#### 回傳

`MediaTrackCapabilities`

視訊軌道的功能

#### 定義於

[html5-qrcode-scanner.ts:393](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L393)

___

### getRunningTrackSettings

▸ **getRunningTrackSettings**(): `MediaTrackSettings`

返回包含執行中視訊每個可約束屬性當前值的對象。

了解更多: https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings

注意：僅當 [()](Html5QrcodeScanner.md#getstate) 返回 [SCANNING](../enums/Html5QrcodeScannerState.md#scanning) 或 [PAUSED](../enums/Html5QrcodeScannerState.md#paused) 時才應呼叫此方法。

**`Throws`**

如果掃描未處於運作狀態，則會出現錯誤。

#### 回傳

`MediaTrackSettings`

執行中視訊的支援的設定。
#### 定義於

[html5-qrcode-scanner.ts:410](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L410)

___

### getState

▸ **getState**(): [`Html5QrcodeScannerState`](../enums/Html5QrcodeScannerState.md)

Gets state of the camera scan.

#### 回傳

[`Html5QrcodeScannerState`](../enums/Html5QrcodeScannerState.md)

state of type [Html5QrcodeScannerState](../enums/Html5QrcodeScannerState.md).

#### 定義於

[html5-qrcode-scanner.ts:325](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L325)

___

### pause

▸ **pause**(`shouldPauseVideo?`): `void`

Pauses the ongoing scan.

Notes:
-   Should only be called if camera scan is ongoing.

**`Throws`**

error if method is called when scanner is not in scanning state.

#### 參數

| Name | Type | Description |
| :------ | :------ | :------ |
| `shouldPauseVideo?` | `boolean` | (Optional, default = false) If `true` the video will be paused. |

#### 回傳

`void`

#### 定義於

[html5-qrcode-scanner.ts:294](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L294)

___

### render

▸ **render**(`qrCodeSuccessCallback`, `qrCodeErrorCallback`): `void`

Renders the User Interface.

#### 參數

| Name | Type | Description |
| :------ | :------ | :------ |
| `qrCodeSuccessCallback` | `QrcodeSuccessCallback` | Callback called when an instance of a QR code or any other supported bar code is found. |
| `qrCodeErrorCallback` | `undefined` \| `QrcodeErrorCallback` | optional, callback called in cases where no instance of QR code or any other supported bar code is found. |

#### 回傳

`void`

#### 定義於

[html5-qrcode-scanner.ts:241](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L241)

___

### resume

▸ **resume**(): `void`

Resumes the paused scan.

If the video was previously paused by setting `shouldPauseVideo`
to `true` in [(shouldPauseVideo)](Html5QrcodeScanner.md#pause),
calling this method will resume the video.

Notes:
-   Should only be called if camera scan is ongoing.
-   With this caller will start getting results in success and error
callbacks.

**`Throws`**

error if method is called when scanner is not in paused state.

#### 回傳

`void`

#### 定義於

[html5-qrcode-scanner.ts:316](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode-scanner.ts#L316)
