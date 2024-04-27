library(factoextra)

iris.labels <- iris$Species
table(iris.labels)

#data
iris_data = iris[1:4] # selecting first 4 col of the data set 
View(iris_data)

#scale data
iris_data_std = scale(iris_data) #scale only the numeric data not factorial data


#distance

iris_dist = dist(iris_data_std)

#hierarchical clustering 

hc.out_iris = hclust(iris_dist,method = "complete")
hc.out_iris

#dendogram
plot(hc.out_iris)


rect.hclust(hc.out_iris,k=3,border =2.5)
