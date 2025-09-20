<h1>Predicting Car Prices (Linear Regression)</h1>
<hr>


<h2>Project Overview</h2>
<p>
This repository implements an end-to-end pipeline for predicting used car prices using linear regression. It covers data cleaning, feature engineering, training and evaluation of regression models, and exporting a trained model for inference.
</p>
<hr>


<h2>Motivation</h2>
<p>
Accurate price prediction helps buyers and sellers make informed decisions, supports pricing engines for marketplaces, and enables automated valuation tools.
</p>
<hr>


<h2>Contents</h2>
<ul>
<li>data/ — raw and processed datasets (CSV)</li>
<li>notebooks/ — exploratory analysis and experiments</li>
<li>src/ — preprocessing, feature engineering, training, and inference scripts</li>
<li>models/ — saved model artifacts and preprocessing pipeline</li>
<li>reports/ — evaluation metrics and plots</li>
<li>README_predict_car_prices.html — this file</li>
</ul>
<hr>


<h2>Dataset</h2>
<p>
Typical columns: listing_id, make, model, year, mileage, engine_size, transmission, fuel_type, condition, price (target). Be sure to check data provenance and handle duplicates or erroneous listings.
</p>
<hr>


<h2>Methodology</h2>
<ol>
<li>Data cleaning — remove invalid rows, handle missing values, correct outliers.</li>
<li>Feature engineering — compute vehicle age from year, encode categorical fields (one-hot or target encoding), transform skewed features (e.g., log mileage or log price if needed).</li>
<li>Modeling — start with Ordinary Least Squares linear regression; also compare regularized variants (Ridge, Lasso) and simple tree-based baselines.</li>
<li>Evaluation — use MAE, RMSE, and R²; perform k-fold cross-validation and examine residuals to check model assumptions.</li>
<li>Deployment — save preprocessing pipeline and trained model (joblib/pickle) and provide a predict script or API stub.</li>
</ol>
<hr>


<h2>How to Run</h2>
<pre>
git clone &lt;repo-url&gt;
cd repo
python -m venv .venv
source .venv/bin/activate # on Windows use .venv\Scripts\activate
pip install -r requirements.txt
python src/train.py --config configs/train_config.yaml
python src/predict.py --input data/new_listings.csv --output predicted_prices.csv
</pre>
<hr>


<h2>Results & Evaluation</h2>
<p>
The repository includes model benchmarks (MAE, RMSE, R²), residual plots, and feature coefficients for interpretability. See reports/ for details.
</p>
