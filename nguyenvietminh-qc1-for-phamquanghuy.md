# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): phamquanghuy        Người kiểm (học viên): nguyenvietminh  
Ngày: 21/11/2026                          Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): phamquanghuy-front.zip, phamquanghuy-fisheye.zip — revision 1 (sha256 khớp manifest)  
Số ảnh kiểm: 6 (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 91  

Ảnh kiểm: A01 (13 nhãn), A04 (11), A08 (30), B03 (18), B06 (11), B08 (8).

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 8 | 1 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 19 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 19 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 19 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 19 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 22 | 1 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 10 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 26 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 16 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 25 | 0 | chính |
| QC1-12 file | lỗi file | 91 | 0 | nhẹ / nặng |

Cách đếm số mục kiểm: QC1-01 = 4 tag × 6 ảnh; QC1-02 = 2 vị trí (L1, R1) × 4 ảnh front/fisheye_front/fisheye_rear (B06, B08 là camera hai bên nên không có L1/R1); QC1-03…06 = số lane; QC1-07 = drivable + crosswalk + road_curb; QC1-08 = đèn; QC1-09 = đèn + biển; QC1-10 = biển; QC1-11 = mọi shape ở B03, B06, B08; QC1-12 = mọi nhãn.

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-02 | B03 | lane L1 (thiếu, không có id) | nặng | Ảnh fisheye_rear chỉ có R1 và R2; vạch đứt trắng bên trái làn đang đi (khoảng x ≈ 490, y ≈ 355 ở điểm gần xe) chưa được vẽ thành L1 |
| 2 | QC1-07 | B08 | drivable direct (thiếu, không có id) | chính | Kế hoạch ảnh B08 là "drivable + lane position=other" nhưng ảnh không có polygon drivable nào |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |

## Quyết định
Lỗi nặng: 1   Lỗi chính: 1 / 91 nhãn = 1,1 %   Lỗi nhẹ: 0   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): Rework  
Lý do (theo luật của phiếu): còn 1 lỗi nặng (QC1-02 thiếu L1 ở B03) → Rework; tỉ lệ lỗi chính 1,1 % không vượt 5 %. Ảnh A01 kiểm không thấy lỗi.  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](docs/qc_severity_road_v1.0.md).
