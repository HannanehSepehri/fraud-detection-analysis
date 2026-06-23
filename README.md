# 🔍 Credit Card Fraud Detection Analysis

تحلیل اکتشافی و ساخت مدل یادگیری ماشین برای شناسایی تقلب در تراکنش‌های کارت بانکی

## 📌 درباره پروژه
این پروژه با استفاده از dataset واقعی Kaggle، الگوهای تراکنش‌های جعلی را تحلیل می‌کند و سه مدل یادگیری ماشین را برای تشخیص تقلب می‌سازد و مقایسه می‌کند.

## 📊 دیتاست
- منبع: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- تعداد تراکنش: ۲۸۴,۸۰۷
- نسبت fraud: ۰.۱۷٪ (داده‌ی به‌شدت نامتوازن)

## 🛠 ابزارها
Python | Pandas | NumPy | Matplotlib | Scikit-learn | imbalanced-learn

## 🔎 یافته‌های تحلیل داده (EDA)
- داده به‌شدت نامتوازن است (۹۹.۸۳٪ تراکنش عادی)
- میانه مبلغ تراکنش‌های جعلی (۹.۲۵ دلار) به‌طور قابل‌توجهی کمتر از میانگین آن‌ها (۱۲۲ دلار) است
- ویژگی‌های V17، V14، V12 بیشترین همبستگی منفی با تقلب دارند
- ویژگی‌های V11، V4، V2 بیشترین همبستگی مثبت با تقلب دارند

## 🤖 مدل‌های یادگیری ماشین

سه مدل Random Forest ساخته و مقایسه شد:

| مدل | Precision | Recall | F1-Score |
|---|---|---|---|
| Baseline | 0.941 | 0.816 | **0.874** |
| + SMOTE | 0.835 | 0.827 | 0.831 |
| + class_weight='balanced' | 0.960 | 0.735 | 0.832 |

**نتیجه کلیدی:** مدل پایه (Baseline) بدون هیچ تنظیم خاصی روی داده نامتوازن، بهترین F1-Score را داشت. این نشان می‌دهد Random Forest به‌طور ذاتی در برابر داده‌های نامتوازن مقاوم است و تکنیک‌های resampling همیشه عملکرد را بهبود نمی‌دهند.

انتخاب مدل نهایی به اولویت کسب‌وکار بستگی دارد:
- کاهش هشدارهای اشتباه → `class_weight`
- شناسایی بیشترین تعداد تقلب → `SMOTE`
- تعادل بین دو هدف → `Baseline`

## 📈 نمودارها
- `plot1_distribution.png` — توزیع تراکنش‌ها
- `plot2_time_analysis.png` — تحلیل زمانی
- `plot3_statistics.png` — آمار توصیفی
- `plot4_correlation.png` — همبستگی ویژگی‌ها
- `model_comparison.png` — مقایسه عملکرد سه مدل

## 🚀 اجرا
```bash
pip install pandas numpy matplotlib scikit-learn imbalanced-learn
jupyter notebook fraud-detection-analysis.ipynb
```
**نکته:** فایل `creditcard.csv` به دلیل حجم باید جدا از [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) دانلود شود.

## 🔭 مراحل بعدی
- مقایسه با XGBoost
- تنظیم هایپرپارامتر با GridSearch
- تحلیل اهمیت ویژگی‌ها (Feature Importance)

## 👩‍💻 توسعه‌دهنده
Hannaneh Sepehri — MSc AI Student
