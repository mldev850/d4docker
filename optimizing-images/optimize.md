Role of Base Images

node:22 --- 1.3 GB
node:alpine --- 205 MB
node:slim --- 218 MB

### IT is not always recommneded to use base images with less size, depends on our use case

Role of Instruction Order

Keep the things which change less often in the beginning of the Docker file 

and put the things which change most in the end of the Docker file.

### This has no effect on size, security but in build time it will have huge impact
### Always remember to check the role of RUN instruction rather than COPY because end of the day it is copying files

Role of Dependencies

 RUN npm ci --only=production   // This will install only dependencies needed for production 

 But if we need any devdependenceis in our project then use Mulit-stage builds

 

