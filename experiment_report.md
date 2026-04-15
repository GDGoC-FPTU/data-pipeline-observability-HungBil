# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600392
**Name:** Nguyen Dong Hung
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu sau ETL chi con record hop le, category da duoc chuan hoa va khong con noise lam lech ket qua. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Agent bi outlier gia cuc lon dan dat, dong thoi bo du lieu con chua duplicate ID, wrong type va null values. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai vi no khong tu dong biet record nao dang tin cay, ma chi dua vao du lieu no doc duoc. Trong `garbage_data.csv`, duplicate ID lam giam do nhat quan cua tap du lieu va co the gay nham lan khi truy vet thuc the. Wrong data type nhu `ten dollars` trong cot price cho thay schema da bi vo, neu logic truy van mo rong hon thi rat de gay loi hoac so sanh sai. Extreme outlier la `Nuclear Reactor` co gia `999999` khien agent chon record nay la "best choice" chi vi gia cao nhat, du record do phi thuc te. Null values va gia tri bang 0 tiep tuc lam giam chat luong nguon tri thuc. Dieu nay cho thay neu khong co validation va observability, agent van co the tra loi rat tu tin nhung sai ban chat.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Trong bai lab nay, prompt khong thay doi, nhung chi can thay du lieu dau vao thi ket qua cua agent da khac hoan toan. Clean data giup agent dua ra cau tra loi hop ly, con garbage data lam agent suy luan tren cac record sai va tao ra ket qua khong dang tin cay. Vi vay, chat luong du lieu la nen tang truoc khi toi uu prompt.
