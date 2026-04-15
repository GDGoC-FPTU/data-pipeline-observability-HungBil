[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574090&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600392
**Name:** Nguyen Dong Hung
**Student Email:** 26ai.hungnd2@vinuni.edu.vn

---

## Mo ta

Bai lab nay yeu cau xay dung ETL pipeline don gian de doc du lieu tu file JSON, kiem tra chat luong du lieu, chuan hoa thong tin va luu ket qua ra CSV. Phan observability duoc the hien bang viec in log so record hop le, so record bi loai va them cot `processed_at` de ghi nhan thoi diem xu ly. Sau do, bai lab tiep tuc stress test agent tren clean data va garbage data de chung minh rang chat luong du lieu dau vao anh huong truc tiep den chat luong cau tra loi.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Tao garbage data
```bash
python generate_garbage.py
```

### Chay Agent Simulation (Stress Test)
```bash
python agent_simulation.py
```

### Chay local autograder
```bash
python -m pytest tests/test_autograder.py -q
```

---

## Cau truc thu muc

```text
solution.py            # ETL Pipeline script
raw_data.json          # Du lieu goc
processed_data.csv     # Output sau khi ETL
generate_garbage.py    # Tao garbage_data.csv
agent_simulation.py    # Stress test agent tren 2 bo du lieu
experiment_report.md   # Bao cao thi nghiem
README.md              # Mo ta bai lam va huong dan chay
```

---

## Ket qua

- ETL doc du lieu thanh cong tu `raw_data.json`.
- Validation giu lai 3 record hop le va loai 2 record loi.
- `processed_data.csv` chua 3 san pham hop le: `Laptop`, `Chair`, `Monitor`.
- Cot `discounted_price` da duoc tinh dung theo cong thuc giam 10 phan tram.
- Cot `processed_at` giup theo doi thoi diem pipeline xu ly batch du lieu.
- Stress test cho thay clean data giup agent tra loi hop ly voi `Laptop at $1200`, trong khi garbage data dan den ket qua sai la `Nuclear Reactor at $999999`.
- Ket luan chinh la quality data quan trong hon quality prompt trong bai toan nay, vi agent phu thuoc truc tiep vao nguon du lieu ma no doc duoc.
