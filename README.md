# git-examples
a set  of git examples
# Git 協作實作紀錄：Fork、Branch、Merge 與 Pull Request

本文件記錄如何透過 Git 指令與 GitHub 介面完成開源協作的四個核心流程。
專案資訊
母專案（Upstream）：https://github.com/se-test-examples/git-examples

子專案（Fork / Origin）：https://github.com/Micha1lyu/git-examples

主要分支：main

功能分支：developGitBranch

1. Fork（建立專案副本）
在 GitHub 上的動作：
瀏覽至母專案頁面：https://github.com/se-test-examples/git-examples

點擊頁面右上角的 Fork 按鈕。

選擇自己的帳號（Micha1lyu），點擊 Create fork。

建立完成後，成功在個人帳號下建立專案副本：https://github.com/Micha1lyu/git-examples。

2. 分支（Branch）
為了不直接修改主分支，建立名為 developGitBranch 的獨立功能分支進行開發。

下達的 Git 指令：
# 1. 建立並切換至新分支 developGitBranch
git checkout -b developGitBranch

# 2. 編輯 README.md 後加入暫存區並提交
git add README.md
git commit -m "docs: 新增協作流程說明文件"

# 3. 將新分支推送到個人的遠端儲存庫 (origin)
git push -u origin developGitBranch
3. Pull Request（發起拉取請求）將個人分支的修改請求審核並合入目標專案中。在 GitHub 上的動作：開啟子專案頁面：https://github.com/Micha1lyu/git-examples。點選頁面上方出現的 Compare & pull request 按鈕。確認比對基準（Base 與 Compare）：若要合入母專案：base repository: se-test-examples/git-examples（base: main）head repository: Micha1lyu/git-examples（compare: developGitBranch）若為個人專案內部整合：base: main $\leftarrow$ compare: developGitBranch輸入 PR 標題與說明，點擊 Create pull request。4. 合併（Merge）將功能分支 developGitBranch 的內容合併回主分支 main。方式 A：透過 GitHub 網頁介面合併（推薦搭配 PR 使用）在剛剛發起的 Pull Request 頁面中，點擊綠色的 Merge pull request。點擊 Confirm merge 完成線上分支合併。方式 B：透過本機終端機指令合併
# 1. 切換回 main 主分支
git checkout main

# 2. 將 developGitBranch 的變更合併至 main
git merge developGitBranch

# 3. 將合併後的 main 分支推送到遠端儲存庫
git push origin main