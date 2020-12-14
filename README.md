# -Tc-
# -ARIMA
对血脂数据进行时序分析，主要内容包括：
1. 数据预处理：异常值检测、处理
2. 影响因素检测：
  1）体检机构正常值范围的比较（上下限均值、上限、下限）；
  2）年龄
  3）性别
3. 截面分析
  1）年
  2）月
  3）不同年龄段
4. 数据标化：按年龄或者性别
5.时序分析
  1）平稳性检测和处理
  2）参数定阶
  3）残差检验
  4）数据预测
  
arma_model = ARMA(data_train,(18,2))
result = arma_model.fit(disp=-1, method='css')
pred = result.predict()
pred_two = result.predict(start= "2019-01-01",end =" 2021-12-31")

plt.plot(pred,color = "orange",label = "fit")
plt.plot(pred_two,color = "red", label = "predict")
plt.plot(data_test,color = "black",label = "orignal_test")
plt.plot(data_train,color = "blue", label = "orignal_train")
plt.legend(loc=0)
