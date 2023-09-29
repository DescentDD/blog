---
title: PyQt初见_强制更新程序
date: 2023-07-04 04:01:21
tags: python
---

# PyQt挺好用

## 上源码

### 瞎搞的强制更新程序，来练手（

```python
import sys
from PyQt5.QtWidgets import QApplication, QMainWindow, QPushButton,QLabel,QProgressBar,QWidget
from PyQt5.QtGui import QFont
from PyQt5.QtCore import QTimer


class updatE(QMainWindow):
    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        self.setGeometry(100, 100, 500, 200)
        self.setWindowTitle("更新")

        self.label=QLabel("发现新版本,在线更新",self)
        self.label.setFont(QFont("Roman times", 15, QFont.Bold))
        self.label.setGeometry(50, 40, 450, 80)

        self.progressbar = QProgressBar(self)
        self.progressbar.setGeometry(50, 140, 250, 40)
        self.progressbar.setVisible(False)
        self.timer=QTimer(self)
        self.timer.timeout.connect(self.update_progressbar)


        self.button = QPushButton("确定", self)
        self.button.setGeometry(320, 140, 150, 40)
        self.button.clicked.connect(self.update)


    def update(self):
        self.progressbar.setVisible(True)
        self.label.setText("")
        self.button.deleteLater()
        self.progressbar.setValue(0)
        self.progressbar.setMaximum(100)
        self.timer.start(100)

    def update_progressbar(self):
        if self.progressbar.value() < 100:
            self.progressbar.setValue(self.progressbar.value() + 1)
        else:
            self.timer.stop()
            self.label.setText("更新完成")
if __name__ == '__main__':
    app = QApplication(sys.argv)
    window = updatE()
    window.show()
    sys.exit(app.exec_())
```



