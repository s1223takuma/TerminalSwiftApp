# CLIで作るSwiftUI App

## プロジェクトの始め方
1. `mkdir 好きな名前`
    - プロジェクトディレクトリを作る
2. `cd [ディレクトリ名]`
    - プロジェクトディレクトリに移動
3. `touch project.yml`
    - 設定ファイルを作成
4. `mkdir [project名]`
    - コードを入れるディレクトリを作成
5. `vim [project名]/[アプリ名]App.swift`
    - アプリの表示設定ファイルの作成
6. `vim [project名]/ContentView.swift`
    - 表示する画面を作成
7. `xcodegen`
    - `ButtonApp.xcodeproj`ファイルを作成<br>
※事前にinstallする必要がある可能性あり
8. `xcrun simctl boot "[任意の機種]"`
    - Simulatorを起動(利用可能機種は`xcrun simctl list devices`で確認)
9. `xcodebuild -project [工程7でできたファイル名].xcodeproj -scheme [scheme名] -destination 'platform=iOS Simulator,name=[任意の機種]' -derivedDataPath build build`
    - simulatorに入れる用の.appファイルを作る
10. `xcrun simctl install booted build/Build/Products/Debug-iphonesimulator/TerminalApp.app`
    - 工程9で作った.appファイルをsimulatorの中にインストール
11. `xcrun simctl launch booted [バンドルID]`
    - 画面に表示
