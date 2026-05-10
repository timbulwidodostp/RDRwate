# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Rate doubly robust estimation for weighted average treatment effects Use RDRwate (WATE) With (In) R Software
install.packages("remotes")
remotes::install_github("yiliu1998/WATE")
install.packages("dplyr")
install.packages("stringi")
install.packages("SuperLearner")
install.packages("glmnet")
install.packages("caret")
library("caret")
library("glmnet")
library("SuperLearner")
library("stringi")
library("dplyr")
library("WATE")
# Estimation Rate doubly robust estimation for weighted average treatment effects Use RDRwate (WATE) With (In) R Software
RDRwate = read.csv("https://raw.githubusercontent.com/timbulwidodostp/RDRwate/main/RDRwate/RDRwate.csv",sep = ";")
A <- RDRwate$A
Y <- RDRwate$Y
X <- RDRwate %>% select(-A, -Y)
v1 <- c(3,5)
v2 <- c(3,5)
beta=TRUE
RDRwate <- RDRwate(A = A, Y = Y, X = X, beta = beta, v1 = v1, v2 = v2, method = "EIF", 
ps.library = c("SL.glm", "SL.glmnet"), out.library = c("SL.glm", "SL.glmnet"), seed = 1)
print(RDRwate)
# Rate doubly robust estimation for weighted average treatment effects Use RDRwate (WATE) With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished