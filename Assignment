library(data.table)
data<-fread('household_power_consumption.txt',sep=';',na.strings = '?')
nrow(data)
ncol(data)
data<-data[Date %in% c('1/2/2007','2/2/2007')]
data$Datetime <- as.POSIXct(paste(data$Date, data$Time), format = "%d/%m/%Y %H:%M:%S")
png("plot1.png", width = 480, height = 480)
p1<-hist(data$Global_active_power, col = "red", main = "Global Active Power", 
     xlab = "Global Active Power (kilowatts)", ylab = "Frequency")
dev.off()
png("plot2.png", width = 480, height = 480)
p2<-plot(data$Datetime, data$Global_active_power, type = "l", 
     xlab = "", ylab = "Global Active Power (kilowatts)")
dev.off()

png("plot3.png", width = 480, height = 480)
plot(data$Datetime, data$Sub_metering_1, type = "l", ylab = "Energy sub metering", xlab = "")
lines(data$Datetime, data$Sub_metering_2, col = "red")
lines(data$Datetime, data$Sub_metering_3, col = "blue")
legend("topright", col = c("black", "red", "blue"), lty = 1, 
       legend = c("Sub_metering_1", "Sub_metering_2", "Sub_metering_3"))
dev.off()


png("plot4.png", width = 480, height = 480)
par(mfrow = c(2, 2))
plot(data$Datetime, data$Global_active_power, type = "l", xlab = "", ylab = "Global Active Power")
plot(data$Datetime, data$Voltage, type = "l", xlab = "datetime", ylab = "Voltage")
plot(data$Datetime, data$Sub_metering_1, type = "l", xlab = "", ylab = "Energy sub metering")
lines(data$Datetime, data$Sub_metering_2, col = "red")
lines(data$Datetime, data$Sub_metering_3, col = "blue")
legend("topright", col = c("black", "red", "blue"), lty = 1, bty = "n",
       legend = c("Sub_metering_1", "Sub_metering_2", "Sub_metering_3"))
plot(data$Datetime, data$Global_reactive_power, type = "l", xlab = "datetime", ylab = "Global Reactive Power")
dev.off()

p<-plot1.png
