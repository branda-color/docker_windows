# 🐳 Laravel 開發環境建置（使用 Docker）  

本專案透過 `docker-compose` 建立一套包含 PHP、MySQL、Nginx 與 phpMyAdmin 的 Laravel 開發環境。  

---
## ⚙️ 前置作業  
需先啟用wsl  
wsl需開啟權限(下在windows指令):Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux   
開啟指定wsl:wsl -d Ubuntu  
查看wsl是否成功指令:wsl -l -v  
1.修改設定  
<img width="590" alt="image" src="https://github.com/user-attachments/assets/265de78f-8616-4da4-aa80-749f8e40c192" />  
2.勾起來源選項  
<img width="382" alt="image" src="https://github.com/user-attachments/assets/9e95f93a-26a8-438f-b70b-3110e1ededd5" />  

---

## 📁 專案目錄結構
├── docker-compose.yml  
├── nginx/  
│ └── default.conf # Nginx 設定檔  
├── php/  
│ └── branda/ # Laravel 專案資料夾  
├── Dockerfile # PHP service 用的 Dockerfile  

---
## 🔧 使用技術  

| 服務        | 描述                        |
|-------------|-----------------------------|
| PHP-FPM     | PHP 8.1，執行 Laravel 應用程式 |
| Nginx       | Web Server，反向代理至 PHP   |
| MySQL       | 資料庫服務（預設 port: 3306） |
| phpMyAdmin  | 資料庫視覺化管理工具（port: 8081） |

---
## 🐳 快速啟動指令  
```bash
# 啟動所有服務並建置
docker-compose up --build -d

# 關閉所有容器
docker-compose down
