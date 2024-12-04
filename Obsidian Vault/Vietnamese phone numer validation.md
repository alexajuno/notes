
### **Định nghĩa số điện thoại hợp lệ tại Việt Nam**

#### 1. **Độ dài số điện thoại**
   - Một số điện thoại hợp lệ ở Việt Nam phải có **10 chữ số** (kể từ khi quy hoạch lại năm 2018).
   - Ví dụ: `0912345678`, `0387654321`.

---

#### 2. **Đầu số hợp lệ (Prefix)**
   - Đầu số (4 chữ số đầu tiên) phải thuộc danh sách đầu số được Bộ Thông tin và Truyền thông quy định.
   - Đầu số cố định cho các nhà mạng di động:
     - **MobiFone**: `070, 076, 077, 078, 079`
     - **VinaPhone**: `081, 082, 083, 084, 085`
     - **Viettel**: `032, 033, 034, 035, 036, 037, 038, 039`
     - **Vietnamobile**: `056, 058`
     - **Gmobile**: `059`
   - Đầu số cố định (điện thoại bàn):
     - Tùy thuộc vào tỉnh/thành phố (e.g., `024` cho Hà Nội, `028` cho TP.HCM).

---

#### 3. **Chỉ chứa ký tự số**
   - Một số điện thoại hợp lệ **chỉ được chứa các ký tự số từ 0 đến 9**.
   - Không được chứa ký tự đặc biệt, chữ cái, hoặc khoảng trắng (e.g., `091@2345678` là không hợp lệ).

---

#### 4. **Không được bắt đầu bằng số 0 ngoài đầu số**
   - Số điện thoại phải bắt đầu bằng **0**, nhưng không được chứa thêm số 0 thừa ở giữa hoặc cuối số (e.g., `0091234567` là không hợp lệ).

---

### **Mô tả dưới dạng quy tắc:**

1. **Cú pháp chung:**
   - Số điện thoại hợp lệ ở Việt Nam có dạng:  
     ```plaintext
     0[3|5|7|8|9]XXXXXXXX
     ```
     Trong đó:
     - `0`: Bắt buộc ở đầu số.
     - `[3|5|7|8|9]`: Đầu số di động.
     - `XXXXXXXX`: 8 chữ số còn lại.

2. **Mẫu regex kiểm tra:**
   - Có thể dùng Regular Expression để kiểm tra:
     ```regex
     ^(0[3|5|7|8|9])\d{8}$
     ```

---

### **Ví dụ minh họa**

#### Số hợp lệ:
- `0381234567` (Viettel)
- `0851234567` (VinaPhone)
- `0701234567` (MobiFone)

#### Số không hợp lệ:
- `09123456` (thiếu số).
- `1234567890` (không bắt đầu bằng số 0).
- `03812a4567` (chứa ký tự không phải số).
---
