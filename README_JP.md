# TD-LaunchPad-Utility
日本語版ドキュメントは英語版から情報を抜粋していたり、更新が遅れていたりすることがあります。
参考までにご覧ください。  
より正確な情報については[README.md](README.md)をご覧ください。

Novation LaunchpadをTouchDesignerと統合し、ボタンのマッピングを簡単に行うためのユーティリティです。

## Compatibility
このツールはNovation Launchpad Pro MK3およびNovation Launchpad Xでの動作が確認されています。他のモデルのLaunchpadでは動作しない可能性があります。toxファイルおよびサンプルプロジェクトファイルはTouchDesignerバージョン2023.11600で作成されました。

## 使用方法

詳細な使用方法や例については、プロジェクトに含まれている`example.toe`ファイルを開いて確認してください。

### Step 1: Launchpadをコンピュータに接続する
- Launchpad Xを使用している場合は、ファクトリープリセットでモードを`Custom 3`に設定します。
- Launchpad Proを使用している場合は、ファクトリープリセットでモードを`Custom 7`に設定します。

### Step 2: TouchDesignerでMIDIデバイスマッパーを設定する
- TouchDesignerの`Dialogues`メニューから`MIDI Device Mapper`を選択します。
- 新しいマッピングを作成し、`Input Device`をLaunchpadに設定します。

### Step 3: Masterコンポーネントを設定する
- TouchDesignerプロジェクト内でこのユーティリティを使用するパスのディレクトリ階層の同じレベルまたは上位レベルに`launchpad_master.tox`を配置します。例えば、`project1`に配置します。

### Step 4: Master COMPを設置する
- `launchpad_master.tox`内で、Launchpadの`Device ID`と`MIDI Channel`を設定し、`Active`をオンにします。この設定は`MIDI Device Mapper`で行うことができます。
- Master COMPが正しく動作しない場合は、Master COMPの`Reset`ボタンを押します。

### Step 5: マップ構成を編集する
- `map_config`を開いてLaunchpad上のコンポーネントを編集します。
- 各コンポーネントはボタンまたはラジオセレクトボタンのグループとして機能します。各コンポーネントの機能、Launchpad上の位置、およびLEDの色を指定できます。
- `control_component` COMPを複製して、Launchpadにコンポーネントを追加します。
- COMPの`Custom`ページを使用してコンポーネントを編集します。コンポーネントはモーメンタリーボタン、トグルボタン、またはラジオセレクトボタンとして設定できます。

#### コンポーネントのパラメータの説明
- **Active:** このトグルを有効にしてコンポーネントをアクティブにします。
- **Parameter Name:** コンポーネントのパラメータの名前。
- **Type:** コンポーネントの機能。`Momentary`、`Toggle`、および`Radio`が利用できます。`Radio`モードはラジオセレクトボタンのように機能します。
- **Position:** Launchpad上のコンポーネントの位置。
- **Size:** Launchpad上のコンポーネントのサイズ（`radio`モードの場合に適用）。
- **Pad LED Color:** LaunchpadのLEDの色を`Hue`および`Value`の2つのパラメータで設定します。オン状態とオフ状態の色を個別に設定できます。

### Step 6: Selectorコンポーネントを設定する
- `launchpad_select.tox`を、Launchpad上のコンポーネントの値を割り当てる場所に配置します。
- `launchpad_select.tox`内の`Custom`ページを開き、以下のパラメータを設定します：
    - **Master OP Name:** `LaunchPad_master`と入力します。
    - **Depth Level:** 現在の`launchpad_select.tox`の位置から`launchpad_master.tox`がある階層までの階層数を設定します。例えば、`launchpad_master.tox`が2階層上にある場合、`Depth Level`を`2`に設定します。

### Step 7: コンポーネントのパラメータを設定する
- コンポーネントのモードを設定し、パラメータ名を付け、位置とサイズ（`radio`モードの場合）を設定し、パッドLEDの色を設定します。

### Step 8: Selector COMPの値を使用する
- `launchpad_select.tox`の出力に接続するか、`launchpad_select.tox`から直接Export CHOPを使用して値を利用します。

## ライセンス
このプロジェクトはMITライセンスの下でライセンスされています。

## 商標
LaunchpadはFocusriteの登録商標です。本プロジェクトは、Focusriteと提携しておらず、Focusriteの承認を受けていません。

## About the Developer
### monoton  
music producer, DJ & VJ, (virtual) experience design, generative visual design  
[Linktree](https://linktr.ee/monoton)
