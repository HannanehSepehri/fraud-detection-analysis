# 🔍 Credit Card Fraud Detection Analysis

تحلیل اکتشافی و ساخت مدل یادگیری ماشین برای شناسایی تقلب در تراکنش‌های کارت بانکی

## 📌 درباره پروژه
این پروژه با استفاده از dataset واقعی Kaggle، الگوهای تراکنش‌های جعلی را تحلیل می‌کند و چندین مدل یادگیری ماشین را برای تشخیص تقلب می‌سازد، تنظیم می‌کند و مقایسه می‌کند.

## 📊 دیتاست
- منبع: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- تعداد تراکنش: ۲۸۴,۸۰۷
- نسبت fraud: ۰.۱۷٪ (داده‌ی به‌شدت نامتوازن)

## 🛠 ابزارها
Python | Pandas | NumPy | Matplotlib | Scikit-learn | imbalanced-learn | XGBoost

## 🔎 یافته‌های تحلیل داده (EDA)
- داده به‌شدت نامتوازن است (۹۹.۸۳٪ تراکنش عادی)
- میانه مبلغ تراکنش‌های جعلی (۹.۲۵ دلار) به‌طور قابل‌توجهی کمتر از میانگین آن‌ها (۱۲۲ دلار) است
- ویژگی‌های V17، V14، V12 بیشترین همبستگی منفی با تقلب دارند
- ویژگی‌های V11، V4، V2 بیشترین همبستگی مثبت با تقلب دارند

## 🤖 مدل‌سازی و نتایج

پنج مدل یادگیری ماشین آموزش داده و مقایسه شدند:

| مدل | Precision | Recall | F1-Score |
|---|---|---|---|
| Random Forest (baseline) | 0.941 | 0.816 | 0.874 |
| Random Forest + SMOTE | 0.835 | 0.827 | 0.831 |
| Random Forest + class_weight='balanced' | 0.960 | 0.735 | 0.832 |
| XGBoost (baseline) | 0.89 | 0.79 | 0.832 |
| **Random Forest (GridSearch tuned)** | **0.94** | **0.82** | **0.874** |

### یافته‌های کلیدی مدل‌سازی
- مدل پایه‌ی Random Forest بدون هیچ تنظیم خاصی روی داده نامتوازن، بهترین F1-Score را داشت — این نشان می‌دهد Random Forest به‌طور ذاتی در برابر داده‌های نامتوازن مقاوم است و تکنیک‌های resampling همیشه عملکرد را بهبود نمی‌دهند
- مدل پایه‌ی Random Forest از XGBoost نیز بهتر عمل کرد (F1: 0.874 در مقابل 0.832)
- Hyperparameter Tuning با GridSearch (`n_estimators=100`, `max_depth=None`) تغییری در F1-Score ایجاد نکرد — مدل پایه از قبل نزدیک به بهینه بود؛ این نشان می‌دهد پیچیده‌تر کردن مدل همیشه پاسخ نیست
- ویژگی‌های V17، V14، V12، V10 و V16 بیشترین نقش را در تشخیص تقلب داشتند (هم‌راستا با تحلیل همبستگی اولیه)

انتخاب مدل نهایی به اولویت کسب‌وکار بستگی دارد:
- کاهش هشدارهای اشتباه → `class_weight` یا `GridSearch tuned`
- شناسایی بیشترین تعداد تقلب → `SMOTE`
- تعادل بین دو هدف → `Baseline`

## 📈 نمودارها
- `plot1_distribution.png` — توزیع تراکنش‌ها
- `plot2_time_analysis.png` — تحلیل زمانی
- `plot3_statistics.png` — آمار توصیفی
- `plot4_correlation.png` — همبستگی ویژگی‌ها
- `model_comparison.png` — مقایسه عملکرد سه مدل اولیه
- `plot5_feature_importance.png` — اهمیت ۱۰ ویژگی برتر مدل

## 🚀 اجرا
```bash
pip install pandas numpy matplotlib scikit-learn imbalanced-learn xgboost
jupyter notebook fraud-detection-analysis.ipynb
```
**نکته:** فایل `creditcard.csv` به دلیل حجم باید جدا از [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) دانلود شود.

## 🔭 مراحل بعدی
- بررسی مدل‌های امنیتی (Adversarial Robustness) برای ارزیابی مقاومت مدل در برابر داده‌های دستکاری‌شده
- استقرار (Deploy) مدل به‌صورت API

## 👩‍💻 توسعه‌دهنده
Hannaneh Sepehri — MSc AI Student
