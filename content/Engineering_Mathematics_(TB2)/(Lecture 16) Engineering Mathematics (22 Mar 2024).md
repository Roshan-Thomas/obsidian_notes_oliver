---
title: Lecture 16
date: 22 Mar 2024
---
# Exam Questions Practice

## Covariance and Correlation

![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240322150254.png]]

**Part a**
$$
\bar x = \frac{5a+10a+15a+10a}{4}=\frac{40a}4=10a
$$
$$
\bar y=\frac{3a+9a+6a+2a}{4}=\frac{20a}4=5a
$$
**Part b**
$$
q_{x,y}=\frac{1}{n-1}\sum_{i=1}^n (X_i-\bar x)(Y_i-\bar y)
$$
$$
\begin{array}{c|c|c}\text{Year}&\text{X sales}&\text{Y sales}\\\hline2019&25&15\\2020&50&45\\2021&75&30\\2022&50&10\end{array}
$$
$$
\bar x=50,\,\,\,\,\,\,\,\,\bar y=25
$$
$$
\begin{split}q_{x,y}&=\frac{1}{4-1}\left[(25-50)(15-25)+(50-50)(45-25)+\dots+(75-50)(30-25)+(50-50)(10-25)\right]\\&=\frac{250+125}{3}\\&=125\end{split}
$$

So we can use two formulae
$$
r=\frac{q_{x,y}}{s_x\,s_y}\,\,\,\,\,\,\,r=\frac{\sum_{i=1}^n(X_i-\bar x)(Y_i-\bar y)}{\sqrt{\sum_{i=1}^n(X_i-\bar x)^2}\sqrt{\sum_{i=1}^n(Y_i-\bar y)^2}}
$$
$$
\begin{split}s_x^2&=\frac{1}{n-1}\sum_{i=1}^n(X_i-\bar x)^2\\&=\frac{1}3 \left[(25-50)^2+(50-50)^2+(75-50)^2+(50-50)^2\right]\\&=\frac 1 3 [25^2+25^2]\\&=\frac{1250}3\end{split}
$$
$$
s_y^2=\frac{1}{n-1}\sum_{i=1}^n(Y_i-\bar y)^2=250
$$
Calculating $r$
$$
r=\frac{q_{x,y}}{s_x\, s_y}=\frac{125}{\sqrt{\frac{1250}{3}}\sqrt{250}}=\frac{\sqrt{15}}{10}
$$
## Correlation and Significance Testing
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240322151402.png]]

**Part a (i)** 
$$
r=\frac{\sum_{i=1}^n(X_i-\bar x)(Y_i-\bar y)}{\sqrt{\sum_{i=1}^n(X_i-\bar x)^2}\sqrt{\sum_{i=1}^n(Y_i-\bar y)^2}}
$$
$$
\bar x=(-4.9-2.7-0.8+0.7+3.1+4.6)\times\frac{1}6=0
$$
$$
\bar y =15.2
$$
$$
\begin{split}\sum_{i=1}^n (X_i-\bar x)(Y_i-\bar y)&=-4.9(29.8-15.2)-2.7(13.8-15.2)+\dots\\&=-8.48\\\sum_{i=1}^n(X_i-\bar x)^2&=4.9^2+2.7^2+0.8^2+0.7^2+3.1^2-4.6^2\\&=63.2\\\sum_{i=1}^n(Y_i-\bar y)^2&=(29.8-15.2)^2+(13.8-15.2)^2+\dots\\&=782.94 \end{split}
$$
$$
r=\frac{-8.48}{\sqrt{63.2}\times\sqrt{782.94}}=-0.0381218
$$

**Part a (ii)**
Fisher transformation defines new normally distributed random variable 
$$
z=\frac{1}2\log\left(\frac{1+r}{1-r}\right)=-0.0381218
$$
with mean
$$
\mu=\frac1 2\log\left(\frac{1+e_0}{1-e_0}\right)
$$
and S.E.
$$
\sigma=\frac{1}{\sqrt{n-3}}=\frac{1}{\sqrt{6.3}}=0.5774
$$
Data is not linearly correlated $\delta=0\Rightarrow \mu=0$

To test our hypothesis - calculate $Z$ value
$$
Z=\frac{z-\mu}{\sigma}=\frac{z}{\sigma}=\frac{-0.0381218}{0.5774}=-0.0661
$$
$$
Z<1.96\text{ True}
$$
## Deriving Normal Equations
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240322152547.png]]

**Part b**
$$
||e||^2=\sum_i e_i^2\,\,\,\,\,\,\,\,e_i=y_i-(\beta_0+\beta_1x_i+\beta_2x_1^2)
$$
$$
||e||^2=\sum_i (y_i-\beta_0-\beta_1x_i-\beta_2x_i^2)
$$
$$
\begin{split}\frac{\partial||e||^2}{\partial\beta_0}&=-2\sum_i(y_i-\beta_0-\beta_1x_i-\beta_2x_i^2)=0\\\frac{\partial||e||^2}{\partial \beta_1}&=-2\sum_ix_i(y_i-\beta_0-\beta_1x_i-\beta_2x_i^2)=0\\\frac{\partial||e||^2}{\partial \beta_2}&=-2\sum_ix_i^2(y_i-\beta_0-\beta_1x_i-\beta_2x_i^2)=0  \end{split}
$$
So,
$$
\begin{split}\sum_i(y_i-\beta_0-\beta_1x_i-\beta_2x_i^2)&=0\\\sum_i\beta_0+\sum_i\beta_1x_i+\sum_i\beta_2x_i^2&=\sum_iy_i\\n\beta_0+\beta_1\sum_i^n x_i+\beta_2\sum_i x_i^2&=\sum_i^n y_i \end{split}\tag{1}
$$
$$
\beta_0\sum_i x_i+\beta_1\sum_i x_i^2+\beta_2\sum_i x_i^3=\sum_ix_iy_i \tag{2}
$$
$$
\beta_0\sum x_i^2+\beta_1\sum x_i^3+\beta_2\sum x_i^4=\sum x_i^2 y_i\tag{3}
$$
## Linear Regression
![[Engineering_Mathematics_(TB2)/images/Pasted_image_20240322153535.png]]
**Part a**
$$
y=a+bx_i
$$
$$
e=a+bx_i-y_i
$$
$$
||e||^2=(a+bx_i-y_i)^2
$$
Using the same method as used previously,
$$
\frac{\partial||e||^2}{\partial a}=2\sum_i(a+bx_i-y_i)=0
$$
$$
\frac{\partial||e||^2}{\partial b}=2\sum_i x_i(a+bx_i-y_i)=0
$$
Dividing the above equations by 2
$$
\begin{split}\sum_i(a+bx_i-y_i)&=0\\na+b\sum x_i&=\sum y_i\end{split}\tag{1}
$$
$$
a\sum x_i+b\sum x_i^2=\sum x_iy_i\tag{2}
$$