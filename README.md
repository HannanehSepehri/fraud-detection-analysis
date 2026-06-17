# 🔍 Credit Card Fraud Detection Analysis

تحلیل اکتشافی روی ۲۸۴,۸۰۷ تراکنش واقعی کارت بانکی برای شناسایی الگوهای تقلب مالی

## 📌 درباره پروژه
این پروژه با استفاده از dataset واقعی Kaggle، الگوهای تراکنش‌های جعلی را در میان داده‌های مالی شناسایی و تحلیل می‌کند.

## 📊 دیتاست
- منبع: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- تعداد تراکنش: ۲۸۴,۸۰۷
- نسبت fraud: ۰.۱۷٪ (داده‌ی به‌شدت نامتوازن)

## 🛠 ابزارها
Python | Pandas | NumPy | Matplotlib

## 🔎 یافته‌های کلیدی
- داده به‌شدت نامتوازن است (۹۹.۸۳٪ تراکنش عادی)
- میانه مبلغ تراکنش‌های جعلی (۹.۲۵ دلار) به‌طور قابل‌توجهی کمتر از میانگین آن‌ها (۱۲۲ دلار) است — نشان‌دهنده چند تراکنش بزرگ استثنایی
- ویژگی‌های V17، V14، V12 بیشترین همبستگی منفی با تقلب دارند
- ویژگی‌های V11، V4، V2 بیشترین همبستگی مثبت با تقلب دارند

## 📈 نمودارها
نمودارهای تولید شده در پوشه پروژه:
- `plot1_distribution.png` — توزیع تراکنش‌ها
- `plot2_time_analysis.png` — تحلیل زمانی
- `plot3_statistics.png` — آمار توصیفی
- `plot4_correlation.png` — همبستگی ویژگی‌ها

## 🚀 اجرا
```bash
pip install pandas numpy matplotlib
jupyter notebook fraud-detection-analysis.ipynb
```
**نکته:** فایل `creditcard.csv` به دلیل حجم باید جدا از [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) دانلود شود.

## 🔭 مراحل بعدی
- ساخت مدل ML (Random Forest, XGBoost)
- مدیریت داده نامتوازن با SMOTE
- ارزیابی با Precision, Recall, F1-Score

## 👩‍💻 توسعه‌دهنده
Hannaneh Sepehri — MSc AI Student
