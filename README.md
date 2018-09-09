# arma


Example code from ARIMA forecasting

library(readxl)
apract <- read_excel("...apract.xlsx", col_types = c("date", "numeric"))
apract_ts = ts(apract[,2],start = c(2018,5,1),frequency = 365)
View(apract_ts)
library("astsa", lib.loc="~/R/win-library/3.5")
library("forecast", lib.loc="~/R/win-library/3.5")
library("tseries", lib.loc="~/R/win-library/3.5")
library("xts", lib.loc="~/R/win-library/3.5")
plot(apract_ts,xlab="date",ylab="day")
plot(diff(apract_ts))
acf2(apract$visits,25)
View(as.numeric(unlist(sarima.for(apract_ts, n.ahead=10, 7, 0, 1, P = 0)$pred)))
a <- sarima.for(apract_ts, n.ahead=10, 7, 0, 1, P = 0)


