#Comments
install.packages("tidyverse")
library(tidyverse)
#In terminal, copy data
cp ~/Documents/MICB425_materials ~/Documents/MICB425_portfolio
#Load data
read.table(file="Saanich.metadata.txt")
#Save data as object in environment
metadata = read.table(file="Saanich.metadata.txt", header=TRUE, row.names=1, sep="\t", na.strings="NAN")
OTU = read.table(file="Saanich.OTU.txt", header=TRUE, row.names=1, sep="\t", na.strings="NAN")

library(dplyr)
#Looking at columns
metadata %>% 
  select(matches("O2|oxygen"))
#Looking at rows
metadata %>% 
  filter(O2_uM == 0) %>% 
  select(Depth_m)

#Saving output of dplyr selection and filtering for oxygen
Oxygen<- metadata %>% 
  filter(O2_uM == 0) %>% 
  select(Depth_m)

#Excercise 2 - methane first
metadata %>% 
  select(matches("CH4|methane"))

#Temperature
metadata %>%
    select(matches("temp"))

#Varaibles are CH4_nM and Temperature_C

metadata %>%
  filter(CH4_nM > 100) %>%
  filter(Temperature_C < 10) %>%
  select(Depth_m, CH4_nM, Temperature_C)
#the above is the same as using "&" b/w 100 and Temperature in one line

#saving output for methane
Methane = metadata %>%
  filter(CH4_nM > 100) %>%
  filter(Temperature_C < 10) %>%
  select(Depth_m, CH4_nM, Temperature_C)

#Mutate function (creating new variables; blue is math function)
metadata %>%
  mutate(N2O_uM = N2O_nM/1000) %>%
  select(N2O_uM, N2O_nM)

library(tidyverse)

metadata %>% 
  select(matches("nM"))

metadata %>% 
  mutate(N2O_uM = N2O_nM/1000) %>% 
  mutate(Std_N2O_uM = Std_N2O_nM/1000) %>% 
  mutate(CH4_uM = CH4_nM/1000) %>% 
  mutate(Std_CH4_uM = Std_CH4_nM/1000) %>%
  select(N2O_nM, N2O_uM, Std_N2O_uM, Std_N2O_nM, CH4_uM, CH4_nM, Std_CH4_uM, Std_CH4_nM)
  
