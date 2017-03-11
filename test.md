# coooooooode
Q1
findNum <- function(y,l){
  ll <- length(y)
  z <- rep(0,ll)
  if (y[1]==1) z[1] <- 1
  for (i in 2:ll) if (y[i]==1) z[i] <- z[i-1]+1
  j <- z>=l
  which(j)-1
}

Q2
raw <- read.delim("data/weather.txt",check.names = F, na.strings = ".")
out <- aggregate(raw[,-c(1:3)],by=list(raw$year,raw$month),FUN=diff)
out <- abs(out)

Q3
library(hflights)
out <- aggregate(hflights$ArrDelay,by=list(hflights$UniqueCarrier,hflights$Year,hflights$Month),
                 FUN=quantile,probs=0.1,na.rm=T)
