### 知道完整路徑
```bash
echo ~
```
### 顯示「你目前所在的資料夾路徑」
```bash
pwd
```
- 初設定值在/c/Users/Top1
### 設定下載路徑
```bash
cd /c/Users/Top1/Documents/GitHub
```
### 建立資料夾
```bash
mkdir /d/MyProjects
```
### 搬移資料夾
```bash
mv 原本的路徑/資料夾名稱 目標路徑
```
```bash
mv /c/Users/你的名字/Desktop/20250425_tvdi /d/MyProjects/
```

### 從 GitHub 把一份完整的專案原始碼下載到自己電腦
```bash
git clone https://github.com/lion0971/20250425_tvdi
```
### 刪除資料夾
- 方法1：直接在檔案總管按 delete（刪除）
- 方法2：
```bash
rm -rf 資料夾名稱
```
rm = remove（刪除）  
-r 和 -f 是 選項（options）：  
-r	recursive（遞迴）刪除	如果是資料夾，要一路把裡面全部一起刪掉。  
-f	force（強制）刪除	不問你確定與否，直接刪掉，不會跳出警告。  
所以，-rf 合起來的意思：不問你直接強制把整個資料夾和裡面所有東西都刪掉。  
如果怕打錯，可以先用 ls 看一下資料夾有沒有真的在那邊，確定完再刪，超安全！  
**因為 rm -rf 很強大（也很危險），輸入的時候一定要小心，確認資料夾名字對了再按下去！不然一不小心刪到別的東西就救不回來了！**
### 刪除同步到 GitHub
- 方法1 push：  
1. 在 VSCode 裡刪除資料夾（用滑鼠刪掉也可以）  
2. 到 Git 提交這個變更（Git 會記得「刪除」也是一個更新！）  
指令流程（在 VSCode terminal 或 Git Bash）：
```bash
git status           # 看看有哪些改動（應該會看到那個資料夾被刪掉了）
git add .            # 把變更加入暫存區（包含刪除動作）
git commit -m "刪除某某資料夾"  # 寫一個 commit 訊息
git push             # 推到 GitHub
```
git add .	加入全部改動（在目前資料夾下）  
git add 檔名	加入指定的單一檔案  
git add 資料夾名	加入指定資料夾內所有檔案的改動  
git add -A 一次加整個專案的變動  
- 方法2：  
1. 打開 VSCode  
2. 進到你的專案資料夾。  
3. 點左側的「Source Control」圖示  
4. 會看到變更（Changes），比如刪掉資料夾就會列出被刪掉的東西。  
5. 點擊「+」把變更加入暫存區「Staged Changes」。  
6. 輸入 Commit 訊息。  
7. Push 到 GitHub  
### 把 GitHub 上的最新改動拉回電腦
- 方法1：
```bash
git pull
```
- 方法2：  
1. 打開 VSCode  
2. 點左邊「Source Control」圖示  
3. 上面有三個小點點「...」（更多選項）點一下！  
4. 找到 Pull 選項，點下去！  

### 改 Git Bash 預設啟動位置
- 方法1：
1. 在桌面找到「Git Bash」這個圖示，→ 右鍵 → 內容(Properties)。  
2. 在內容裡找到一個欄位叫 「起始位置 (Start in)」
```ruby
%HOMEDRIVE%%HOMEPATH%
```
3. 改成你想要自動進去的資料夾路徑！  
記得是「反斜線」"\", 因為這邊是 Windows 的路徑格式喔～  
- 方法2：
1. 複製一個 Git Bash 的捷徑  
2. 右鍵 → 內容  
3. 只改那個「起始位置」  
4. 然後自己改個名字，比如叫「Git Bash (D槽專用)」  
這樣你桌面上就有兩個 Git Bash可以選啦！  
### Public 的 repo，改成 Private
##### 進到 repo ➔ 點「Settings」➔ 找到「Danger Zone」➔ 找「Change visibility」➔ 選「Make private」
1. 到 GitHub 個人設定頁面拿 Token
- 進到 GitHub
- 點你的大頭貼 ➔ 「Settings」
- 左邊選「Developer settings」
- 點「Personal access tokens」➔ 「Tokens (classic)」
- 點「Generate new token (classic)」
2. 建立 Token
設定一些基本的東西：

- Note：自己備註一下，例如「For VSCode」

- Expiration：可以設一個過期時間（比如 30天、90天、無限）

- Scopes 權限：勾選最基本就好，例如：  
  repo（管理你的 private repo）  
  workflow（如果有自動化流程） （一般打勾 repo 就夠了）  
按「Generate token」
3. 複製Token
- 產生完會看到一串長長的英數字
- 馬上複製下來存好（因為離開頁面就看不到了），可以暫時存在記事本（但注意安全喔！）
4. Push 時使用這個 Token
當你在 VSCode 或 Git Bash push，出現問：  
Username ➔ 輸入你的 GitHub 帳號  
Password ➔ 貼上剛剛的 Token！（不是你平常登入的密碼喔！）
### 在某個資料夾的終端機（Terminal）裡，根據 requirements.txt 檔案安裝裡面列出的所有 Python 套件
'''terminal
pip install -r requirements.txt
'''

### 開啟flask
'''terminal
flask --app 網頁名稱(不用副檔名) run
'''

### 開啟檔案儲存後自動更新網頁功能
'''terminal
flask --app 網頁名稱(不用副檔名) run --debug
'''

