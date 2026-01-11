# GAME DESIGN DOCUMENT (GDD)

## 1. Thông tin chung

**Tên game:** Bow Hit
**Thể loại:** Casual / Arcade
**Nền tảng:** Mobile (Android / iOS)
**Engine:** Unity 2022 LTS
**Camera:** 2D – Orthographic
**Đối tượng người chơi:** Mọi lứa tuổi
**Phong cách:** Đơn giản, dễ chơi – khó thành thạo

---

## 2. Tổng quan gameplay

Bow Hit là game bắn tên casual, người chơi sử dụng **cung tên** để bắn các **mũi tên** ghim vào **bàn gỗ tròn đang xoay**. Mục tiêu là:

* **Ghim đủ số mũi tên yêu cầu**
* **Bắn trúng đủ số táo xuất hiện trên bàn gỗ**

Khi hoàn thành cả hai điều kiện → **WIN**.

Người chơi sẽ **THUA** nếu:

* Bắn trúng mũi tên đã ghim trước đó

---

## 3. Cơ chế chơi chính

### 3.1 Điều khiển

* **Tap màn hình:** Bắn 1 mũi tên
* Không có joystick → 1 tay chơi được

### 3.2 Bàn gỗ (Target)

* Xoay trái / phải
* Tốc độ xoay tăng dần theo level
* Có thể:

  * Xoay đều
  * Đổi chiều bất ngờ
  * Dừng – xoay lại

### 3.3 Mũi tên

* Số lượng mũi tên mỗi màn là **giới hạn**
* Có nhiều skin mũi tên (mua bằng đá quý)

### 3.4 Táo

* Xuất hiện ngẫu nhiên trên bàn gỗ
* Bắn trúng táo → nhận **đá quý**
* Một số level yêu cầu **bắn trúng đủ X táo** mới được WIN

---

## 4. Điều kiện thắng / thua

### Nguyên tắc kiểm tra kết quả

* **CHỈ kiểm tra Win / Lose khi người chơi đã bắn HẾT số mũi tên hiện có**
* Trong lúc còn mũi tên → game **KHÔNG kết thúc**

### Thắng (Win)

* Sau khi bắn hết mũi tên:

  * Đã **ghim đủ số mũi tên yêu cầu**
  * Và **bắn trúng đủ số táo yêu cầu**

### Thua (Lose)

* Sau khi bắn hết mũi tên:

  * **KHÔNG đạt đủ số mũi tên yêu cầu**
  * Hoặc **KHÔNG bắn trúng đủ số táo yêu cầu**

---

## 5. Cấu trúc Scene

### 5.1 Load Scene

* Hiển thị logo Bow Hit
* Thanh loading
* Khởi tạo:

  * Ads (AdMob)
  * Audio Manager
  * Save Data

### 5.2 Home Scene

* Logo game
* Button:

  * Play
  * Shop
  * No Ads
  * Setting
* Hiển thị:

  * Số đá quý hiện có

### 5.3 Gameplay Scene

* Bàn gỗ + mũi tên
* UI:

  * Số mũi tên còn lại
  * Táo cần bắn
  * Pause button

---

## 6. Hệ thống Popup

### 6.1 PopupPause

* Resume
* Restart
* Home

### 6.2 PopupLose

* Hiển thị điểm / level
* Button:

  * Xem quảng cáo → **Revive (tiếp tục chơi)**
  * Dùng đá quý để hồi sinh
  * Chơi lại
  * Về Home

### 6.3 PopupWin

* Hiển thị đá nhận được
* Button:

  * Xem quảng cáo → **x2 đá thưởng**
  * Next Level

### 6.4 PopupShop

* Mua:

  * Theme bàn gỗ
  * Skin cung
  * Skin mũi tên
  * Mua thêm đá quý

### 6.5 PopupBigShop

* Gói đá lớn
* Bundle ưu đãi

### 6.6 PopupNoAds

* Mua gói **No Ads** (Remove Ads)

### 6.7 PopupSetting

* Bật / tắt:

  * Nhạc nền
  * Âm thanh
  * Rung

---

## 7. Monetization

### 7.1 Quảng cáo (AdMob)

* **Rewarded Ads**:

  * Nhận thêm mũi tên
  * Revive khi thua
  * x2 đá khi thắng

* **Interstitial Ads**:

  * Hiển thị sau X level
  * Không hiển thị nếu đã mua No Ads

### 7.2 In-App Purchase (IAP)

* No Ads
* Mua đá quý
* Bundle skin + đá

---

## 8. Tiền tệ trong game

### 8.1 Đá quý (Gems)

* Nhận từ:

  * Bắn trúng táo
  * Thắng level
  * Xem quảng cáo
* Dùng để:

  * Mua skin
  * Hồi sinh nếu không xem ads

---

## 9. Âm thanh & Nhạc

### 9.1 Sound Effect (SFX)

* Mũi tên bắn
* Mũi tên ghim vào gỗ
* Bắn trúng táo
* Thắng / Thua
* Click UI

### 9.2 Nhạc nền (BGM)

* Nhạc Home
* Nhạc Gameplay (nhẹ, lặp)

---

## 10. Progression & Level Design

* Level tăng dần độ khó:

  * Tốc độ xoay nhanh hơn
  * Nhiều mũi tên hơn
  * Nhiều táo hơn
* Có Boss Level:

  * Bàn gỗ nhỏ
  * Xoay rất nhanh

---

## 11. Lưu trữ & dữ liệu

* Save:

  * Level hiện tại
  * Đá quý
  * Skin đã mua
  * Trạng thái No Ads

---

## 12. Mục tiêu thiết kế

* Chơi nhanh – dễ hiểu trong 3 giây
* Gây nghiện ngắn hạn
* Phù hợp casual player
* Tối ưu quảng cáo nhưng không gây khó chịu

---

**End of GDD – Bow Hit**
