
```

# install package 
library(devtools)
install_github("sakuramomo1005/bi-ADMM")

# toy parameter
nu1 = nu2 = nu3 = gamma_1 = gamma_2 = 0.1
kk = 5; phi = 0.5

# data generation
set.seed(123)
X = data_gen(n = 100, p = 80)

# run bi-ADMM algorithm (slow version)
t1 = Sys.time()
res1 = biADMM(X, nu1, nu2, gamma_1, gamma_2, kk, phi, niter = 10, tol = 0.1, output = 1)
t2 = Sys.time()

# run bi-ADMM algorithm (faster version)
t3 = Sys.time()
res2 = biADMM.speed(X, nu1, nu2, gamma_1, gamma_2, kk, phi, niters = 10, tol = 0.1, output = 1)
t4 = Sys.time()

# run biC-ADMM algorithm (slow version)
t5 = Sys.time()
res3 = biC.ADMM(X, nu1, nu2, nu3, gamma_1, gamma_2, kk, phi, niter = 10, tol = 0.1, output = 1)
t6 = Sys.time()

# run biC-ADMM algorithm (faster version)
t7 = Sys.time()
res4 = biC.ADMM.speed(X, nu1, nu2, nu3, gamma_1, gamma_2, kk, phi, niters = 10, tol = 0.1, output = 1)
t8 = Sys.time()

```
