# GitHub Pages 公開手順ガイド

作成したプロフィールページ（HTML）を、GitHub Pagesを使って無料で公開する手順です。

## 方法A：GitHub CLIを使う（おすすめ）
ターミナル操作だけで完結する方法です。

1.  **GitHub CLIのインストール**
    ```bash
    brew install gh
    ```

2.  **ログイン**
    ```bash
    gh auth login
    # 画面の指示に従ってブラウザで認証してください
    ```

3.  **リポジトリ作成とプッシュ**
    ```bash
    cd "/Users/bunchaca/product/2nd-Brain/99_Sbox/Profile_Page"
    git init
    git add .
    git commit -m "Initial commit"
    gh repo create profile-akira --public --source=. --push
    ```

4.  **GitHub Pagesの設定**
    *   ブラウザで作成したリポジトリを開く（`gh browse` で開けます）。
    *   [Settings] > [Pages] に移動。
    *   Branch: `main` / `/(root)` に設定して [Save]。

---

## 方法B：手動で設定する
ブラウザでリポジトリを作ってから、コマンドでアップロードする方法です。

1.  **GitHubでリポジトリ作成**
    *   GitHubにログインし、新規リポジトリ（例: `profile-akira`）を作成する。
    *   「Public」を選択する。

2.  **コマンド実行**
    ターミナルで以下を実行します：
    ```bash
    cd "/Users/bunchaca/product/2nd-Brain/99_Sbox/Profile_Page"
    git init
    git add .
    git commit -m "Initial commit"
    git branch -M main
    git remote add origin [作成したリポジトリのURL]
    git push -u origin main
    ```

3.  **GitHub Pagesの設定**
    *   GitHub上で [Settings] > [Pages] に移動。
    *   Branch: `main` / `/(root)` に設定して [Save]。

---

## 完了後
数分待つと、以下のURLで公開されます。
`https://[あなたのユーザー名].github.io/profile-akira/`
