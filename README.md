# 大樂透隨機獎號產生, Big Lotto Random Drawing

## 下載和執行 Clone & Run
```bash
git clone https://github.com/TaiwanLottery/BigLottoRandomDrawing
cd BigLottoRandomDrawing
python3 BigLottoRandomDrawing                # Python version requirement: 3.6
```

## 輸入 Input
```bash
# 分別輸入對應數值，或按enter跳過來使用預設值
  Start ID(1yy000nnn, default=1):        # 開始期號(e.g., 108000020)，未輸入則從1開始編號
  Period Count(1~n, default=1):          # 產生期數(e.g., 8)，會從該期數與日期開始產生8組號碼，未輸入則產生1組
  Start Date(20yymmdd, default=None):    # 開始的日期(e.g., 20190212)，需是星期二或星期五，未輸入則為空
  Print Distribution(y/n, default=y):    # 是否印出49個號碼的分布，輸入n/N來關閉，否則印出
```
<img src="https://i.imgur.com/dDgbVhD.png" width="400"/>

## 運作流程 Program Flow
使用secrets的SystemRandom().sample()  
隨機產生【期數 × 1萬】組號碼，並從中隨機取出【期數】組  

使用datetime的date來推算星期、timedelta來推算所有開獎日期
