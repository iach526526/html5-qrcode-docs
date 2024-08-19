---
sidebar_position: 1
---

[html5-qrcode](../) / Html5Qrcode

# Class: Html5Qrcode

用於配置基於網頁的 QR 碼和條碼掃描器的低級 API。

支援鏡頭掃描和基於檔案的掃描 API。

根據配置，該類將幫助在提供的父 HTML 容器中渲染程式碼掃描 UI。

## 目錄

### Constructors

- [constructor](Html5Qrcode.md#constructor)

### Methods

- [applyVideoConstraints](Html5Qrcode.md#applyvideoconstraints)
- [clear](Html5Qrcode.md#clear)
- [getRunningTrackCameraCapabilities](Html5Qrcode.md#getrunningtrackcameracapabilities)
- [getRunningTrackCapabilities](Html5Qrcode.md#getrunningtrackcapabilities)
- [getRunningTrackSettings](Html5Qrcode.md#getrunningtracksettings)
- [getState](Html5Qrcode.md#getstate)
- [pause](Html5Qrcode.md#pause)
- [resume](Html5Qrcode.md#resume)
- [scanFile](Html5Qrcode.md#scanfile)
- [scanFileV2](Html5Qrcode.md#scanfilev2)
- [start](Html5Qrcode.md#start)
- [stop](Html5Qrcode.md#stop)
- [getCameras](Html5Qrcode.md#getcameras)

## Constructors

### constructor

• **new Html5Qrcode**(`elementId`, `configOrVerbosityFlag?`)

初始化程式碼掃描器。
#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| elementId | string | Id of the HTML element. |
| configOrVerbosityFlag? | boolean \| [Html5QrcodeFullConfig](../interfaces/Html5QrcodeFullConfig.md) | optional, config object of type [Html5QrcodeFullConfig](../interfaces/Html5QrcodeFullConfig.md) or a boolean verbosity flag (to maintain backward compatibility). If nothing is passed, default values would be used. If a boolean value is used, it'll be used to set verbosity. Pass a config value to configure the Html5Qrcode scanner as per needs. Use of configOrVerbosityFlag as a boolean value is being deprecated since version 2.0.7. TODO(mebjas): Deprecate the verbosity boolean flag completely. |
#### 參數

| 名稱 | 類型 | 描述 |
| :------ | :------ | :------ |
| `elementId` | `string` | HTML 元素的 ID。 |
| `configOrVerbosityFlag?` | `boolean` \| [`Html5QrcodeFullConfig`](../interfaces/Html5QrcodeFullConfig.md) | 可選，`Html5QrcodeFullConfig` 類型的配置對象或布林型詳細訊息標誌（以維持向後兼容）。如果未傳遞任何值，則將使用預設值。如果使用布林值，它將用於設定詳細訊息。根據需要的設定傳遞設定值設定 Html5Qrcode 掃描器。自版本 2.0.7 起，不建議使用 configOrVerbosityFlag 作為布林值。 TODO(mebjas)：完全棄用詳細布林標誌。

#### 定義於

[html5-qrcode.ts:313](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L313)

## 方法

### applyVideoConstraints

▸ **applyVideoConstraints**(`videoConstaints`): `Promise`<`void`\>

對來自鏡頭的執行影片軌道應用影片約束。

重要事項：
1. 只有在進行基於鏡頭的掃描時，才必須呼叫此方法。
2. 在掃描器執行時更改 `aspectRatio` 尚不支援。

**`Throws`**

如果掃描不在執行狀態，則拋出錯誤。

#### 參數

| 名稱 | 類型 |
| :------ | :------ |
| `videoConstaints` | `MediaTrackConstraints` |

#### 回傳

`Promise`<`void`\>

一個 Promise，若傳遞的約束已成功應用則成功，否則失敗。

#### 定義於

[html5-qrcode.ts:829](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L829)

___

### clear

▸ **clear**(): `void`

清除現有的畫布。

注意：如果有正在進行的網路鏡頭掃描，需要在呼叫此方法之前明確關閉，否則會拋出異常。


#### 回傳

`void`

#### 定義於

[html5-qrcode.ts:758](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L758)

___

### getRunningTrackCameraCapabilities

▸ **getRunningTrackCameraCapabilities**(): [`CameraCapabilities`](../interfaces/CameraCapabilities.md)

Returns [CameraCapabilities](../interfaces/CameraCapabilities.md) of the running video track.

TODO(minhazav): Document this API, currently hidden.
返回執行追蹤的影片 [CameraCapabilities](../interfaces/CameraCapabilities.md)。

TODO(minhazav): 文檔化此 API，目前為隱藏。
**`Throws`**

如果掃描不在運行狀態，則拋出錯誤。

#### 回傳

[`CameraCapabilities`](../interfaces/CameraCapabilities.md)

capabilities of the running camera.
運行中相機的能力
#### Defined in

[html5-qrcode.ts:811](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L811)

___

### getRunningTrackCapabilities

▸ **getRunningTrackCapabilities**(): `MediaTrackCapabilities`

Returns the capabilities of the running video track.

Read more: https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getConstraints

Important:
 1. Must be called only if the camera based scanning is in progress.

**`Throws`**

error if the scanning is not in running state.

#### 回傳

`MediaTrackCapabilities`

capabilities of the running camera.

#### Defined in

[html5-qrcode.ts:782](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L782)

___

### getRunningTrackSettings

▸ **getRunningTrackSettings**(): `MediaTrackSettings`

Returns the object containing the current values of each constrainable
property of the running video track.

Read more: https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings

Important:
 1. Must be called only if the camera based scanning is in progress.

**`Throws`**

error if the scanning is not in running state.

#### 回傳

`MediaTrackSettings`

settings of the running media track.

#### Defined in

[html5-qrcode.ts:799](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L799)

___

### getState

▸ **getState**(): [`Html5QrcodeScannerState`](../enums/Html5QrcodeScannerState.md)

Gets state of the camera scan.

#### 回傳

[`Html5QrcodeScannerState`](../enums/Html5QrcodeScannerState.md)

state of type ScannerState.

#### Defined in

[html5-qrcode.ts:539](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L539)

___

### pause

▸ **pause**(`shouldPauseVideo?`): `void`

Pauses the ongoing scan.

**`Throws`**

error if method is called when scanner is not in scanning state.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `shouldPauseVideo?` | `boolean` | (Optional, default = false) If true the video will be paused. |

#### 回傳

`void`

#### Defined in

[html5-qrcode.ts:480](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L480)

___

### resume

▸ **resume**(): `void`

Resumes the paused scan.

If the video was previously paused by setting `shouldPauseVideo``
to `true` in [(shouldPauseVideo)](Html5Qrcode.md#pause), calling
this method will resume the video.

Note: with this caller will start getting results in success and error
callbacks.

**`Throws`**

error if method is called when scanner is not in paused state.

#### 回傳

`void`

#### Defined in

[html5-qrcode.ts:508](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L508)

___

### scanFile

▸ **scanFile**(`imageFile`, `showImage?`): `Promise`<`string`\>

Scans an Image File for QR Code.

This feature is mutually exclusive to camera-based scanning, you should
call stop() if the camera-based scanning was ongoing.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `imageFile` | `File` | a local file with Image content. |
| `showImage?` | `boolean` | if true the Image will be rendered on given element. |

#### 回傳

`Promise`<`string`\>

Promise with decoded QR code string on success and error message
on failure. Failure could happen due to different reasons:
  1. QR Code decode failed because enough patterns not found in image.
  2. Input file was not image or unable to load the image or other image
     load errors.

#### Defined in

[html5-qrcode.ts:615](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L615)

___

### scanFileV2

▸ **scanFileV2**(`imageFile`, `showImage?`): `Promise`<[`Html5QrcodeResult`](../interfaces/Html5QrcodeResult.md)\>

Scans an Image File for QR Code & returns [Html5QrcodeResult](../interfaces/Html5QrcodeResult.md).

This feature is mutually exclusive to camera-based scanning, you should
call stop() if the camera-based scanning was ongoing.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `imageFile` | `File` | a local file with Image content. |
| `showImage?` | `boolean` | if true the Image will be rendered on given element. |

#### 回傳

`Promise`<[`Html5QrcodeResult`](../interfaces/Html5QrcodeResult.md)\>

Promise which resolves with result of type
[Html5QrcodeResult](../interfaces/Html5QrcodeResult.md).

 This is a WIP method, it's available as a public method but not
documented.
TODO(mebjas): Replace scanFile with ScanFileV2

#### Defined in

[html5-qrcode.ts:638](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L638)

___

### start

▸ **start**(`cameraIdOrConfig`, `configuration`, `qrCodeSuccessCallback`, `qrCodeErrorCallback`): `Promise`<``null``\>

Start scanning QR codes or bar codes for a given camera.

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `cameraIdOrConfig` | `string` \| `MediaTrackConstraints` | Identifier of the camera, it can either be the camera id retrieved from Html5Qrcode#getCameras() method or object with facing mode constraint. |
| `configuration` | `undefined` \| [`Html5QrcodeCameraScanConfig`](../interfaces/Html5QrcodeCameraScanConfig.md) | Extra configurations to tune the code scanner. |
| `qrCodeSuccessCallback` | `undefined` \| `QrcodeSuccessCallback` | Callback called when an instance of a QR code or any other supported bar code is found. |
| `qrCodeErrorCallback` | `undefined` \| `QrcodeErrorCallback` | Callback called in cases where no instance of QR code or any other supported bar code is found. |

#### 回傳

`Promise`<``null``\>

Promise for starting the scan. The Promise can fail if the user
doesn't grant permission or some API is not supported by the browser.

#### Defined in

[html5-qrcode.ts:360](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L360)

___

### stop

▸ **stop**(): `Promise`<`void`\>

Stops streaming QR Code video and scanning.

#### 回傳

`Promise`<`void`\>

Promise for safely closing the video stream.

#### Defined in

[html5-qrcode.ts:548](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L548)

___

### getCameras

▸ `Static` **getCameras**(): `Promise`<[`CameraDevice`](../interfaces/CameraDevice.md)[]\>

Returns list of [CameraDevice](../interfaces/CameraDevice.md) supported by the device.

#### 回傳

`Promise`<[`CameraDevice`](../interfaces/CameraDevice.md)[]\>

array of camera devices on success.

#### Defined in

[html5-qrcode.ts:767](https://github.com/mebjas/html5-qrcode/blob/600717e/src/html5-qrcode.ts#L767)
