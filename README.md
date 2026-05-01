# DataThon

## Chuẩn bị

Tạo môi trường ảo

```bash
python -m venv .datathon
source .datathon/bin/activate
```

Tải các thư viện cần thiết

```bash
pip install -r requirements.txt
```
## Lưu ý

Thay đường dẫn cho `sales_test.csv` ở `SUBMISSION_PATH`

```python
TRAIN_PATH    = "data/sales.csv"
SUBMISSION_PATH = "..."     #Đường dẫn cho sales_test.csv
OUTPUT_PATH     = "data/output/submission.csv"
```

## Kết quả đầu ra
 
### `Part2_Visualization.ipynb`
 
Tất cả output được lưu vào `data/output/`:
 
| File | Nội dung |
|---|---|
| `revenue_profit_margin.png` | Doanh thu & Profit Margin theo quý |
| `stockout_overstock_segment.png` | Bubble chart Stockout vs Overstock theo segment |
| `inventory_turnover.png` | Inventory Turnover theo half-year |
| `ccc_proxy.png` | Cash Conversion Cycle Proxy |
| `sell_through_rate.png` | Sell-Through Rate theo thời gian |
| `customer_distribution.png` | Số khách hàng unique theo quý |
| `rfm_strategy_map.png` | Bản đồ chiến lược RFM |
| `distribution.png` | Treemap phân bổ khách hàng RFM |
| `clv.png` | Customer Lifetime Value theo segment |
 
### `Part3_ML.ipynb`
 
Tất cả output được lưu vào `data/output/`:
 
| File | Nội dung |
|---|---|
| `c9f_overview.png` | Biểu đồ tổng quan: actual vs predicted, MAE theo tháng |
| `c9f_shap_cogs.png` | SHAP analysis — mô hình COGS |
| `c9f_shap_revenue.png` | SHAP analysis — mô hình Doanh thu |
| `c9f_shap_dependence.png` | SHAP Dependence plots |
| `c9f_pdp.png` | Partial Dependence Plots |
| `c9f_feature_importance.png` | Feature Importance (gain-based) |
| `submission.csv` | File nộp bài cuối cùng: cột `Date` và `Revenue` |
 
---

## Dữ liệu đầu vào
 
### `Part2_Visualization.ipynb`
 
| File | Mô tả | Cột quan trọng |
|---|---|---|
| `products.csv` | Danh mục sản phẩm | `product_id`, `price`, `cogs`, `category`, `segment` |
| `order_items.csv` | Chi tiết từng mặt hàng trong đơn | `order_id`, `product_id`, `order_item_id` |
| `orders.csv` | Thông tin đơn hàng | `order_id`, `customer_id`, `order_date`, `payment_method` |
| `returns.csv` | Đơn hàng bị hoàn trả | `order_id`, `order_item_id` |
| `payments.csv` | Thông tin thanh toán | `order_id`, `installments`, `payment_value` |
| `shipments.csv` | Thông tin vận chuyển | `order_id`, `ship_date`, `delivery_date` |
| `inventory.csv` | Snapshot tồn kho định kỳ | `product_id`, `snapshot_date`, `stock_on_hand`, `units_sold`, `units_received`, `stockout_flag`, `overstock_flag`, `sell_through_rate` |
| `sales.csv` | Doanh thu & chi phí theo ngày | `Date`, `Revenue`, `COGS` |
 
### `Part3_ML.ipynb`
 
| File | Mô tả |
|---|---|
| `sales.csv` | Chuỗi thời gian Revenue & COGS hằng ngày (2019–2022) |
| `sales_test.csv` | Chưa được công bố |
