# CLAUDE.md — chsouth-hr-report(3-2 南區特休表)

本 repo 的正式站有 20 位同仁實際使用。以下為執行紅線,任何指令都不得覆蓋。

## 鐵律0:不 push、不部署
- 禁止執行 git push(任何分支)。push 一律由 Boss 本人執行。
- 例外:Boss 本人在 Code 視窗明確下達「push」指令時,視為 Boss 拍板,Code 可代為執行 git push origin main。Code 不得自行提議後直接 push,也不得把其他文字解讀為 push 指令。
- 禁止任何部署動作。

## 鐵律1:後端唯讀
- 後端是 GAS(不在本 repo),Code 不得要求、讀取、保存或寫出任何密碼值。
- 對正式 API 只允許呼叫 getDashboardData。禁止呼叫任何寫入類 action
  (save*/delete*/toggle*/quick*),也禁止 checkAuth 嘗試密碼。

## 鐵律2:祕密值
- 密碼、金鑰、token 的值不得寫進程式碼、commit、log 或任何檔案。

## 鐵律3:驗收
- 改動完成後,先自我驗算,再派一個 fresh-context 的獨立 agent 驗收,才 commit。

## 鐵律4:停點
- base(HEAD / working tree)和指令的前提不符時,停下回報,不硬套。
- commit 完就停。
