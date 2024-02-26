Examples of S3 and S4
> s3_class <- list(
+   name = "s3_example",
+   data = NULL,
+   initialize = function(data) {
+     if (!is.data.frame(data)) {
+       stop("Input must be a data frame")
+     }
+     # Store the data in the 'data' slot
+     this <- list(data = data)
+     class(this) <- "s3_example"
+     return(this)
+   }
+ )
> 
> # Create an object of S3 class
> s3_object <- s3_class$initialize(datasets::iris)
> # Define an S4 class
> setClass("s4_example",
+          slots = list(
+            data = "data.frame"
+          )


# Define the "iris_class"
> setClass("iris_class", slots = list())
> 
> # Assign the "iris_class" to the iris dataset
> class(iris) <- "iris_class"
> 
> # Define the S4 class
> setClass("s4_example",
+          slots = list(
+            data = "iris_class"  # Adjusted to match the defined class
+          )
+ )
> 
> # Create an object of the S4 class
> s4_object <- new("s4_example", data = iris)
