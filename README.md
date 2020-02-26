# Java Matrix Algebra :alien:

A matrix algebra implementation in Java.

## Importing

Source: Matrix.java <br />
Compile:
```sh
> javac Matrix.java
```
Import:
```Java

public class test {

  public static void main(String[] args) {
    Matrix mx = new Matrix();
  }
}


```

## Primary Functions

#### Multiply
````Java

  mx.MultiplyMatrix(double[][] X, double[][] Y);

````

#### Transpose

#### Row Reduce

#### Diagonalize

#### Inverse

#### Determenant

#### Trace

#### Add/Subtract Two Matrices

#### Multiply matrix by coefficient

#### Get Diagonal Of Matrix

#### Give a power to each variable of a matrix

#### Give a coefficient a matrix as an exponent



## Examples

### Mean
![Equation](https://latex.codecogs.com/gif.latex?%5Chat%7B%5Cmu%7D%3D%5Cdfrac%7B1%7D%7Bm%7D1%5ETX)
```Java
public static void MeanExample(){
    Matrix np = new Matrix();
    StatPack sp = new StatPack();
    double[][] X = {{6, 6, 7, 2},
                    {14, 3, 51, 6},
                    {4, 13, 25, 18},
                    {24, 31, 15, 36},
                    {4, 13, 5, 2},
                    {4, 3, 51, 16}};

    double[][] mu = sp.Mean(X);
    np.PrintM(mu);
}
```

### Covariance & Correlation Matrix
Covariance
![Equation](https://latex.codecogs.com/gif.latex?%5CSigma%20%3D%20%5Cdfrac%7B1%7D%7Bm-1%7D%28X-%5Chat%7BX%7D%29%5ET%28X%20-%20%5Chat%7BX%7D%29) <br />

Correlation
![Equation](https://latex.codecogs.com/gif.latex?%5Cbegin%7Bmatrix%7D%20H%3D%5Csqrt%7Bdiag%5Cbig%28%7B%5CSigma%7D%5Cbig%29%7D%20%26%26%20%5Crho%20%3D%20%5Cdfrac%7B%5CSigma_%7Bi%2C%20j%7D%7D%7B%5BHH%5ET%5D_%7Bi%2C%20j%7D%7D%20%5Cend%7Bmatrix%7D)

```Java
public static void CovarExample(){
    double[][] X = {{6, 6, 7, 2},
                    {14, 3, 51, 6},
                    {4, 13, 25, 18},
                    {24, 31, 15, 36},
                    {4, 13, 5, 2},
                    {4, 3, 51, 16}};

    double[][] covariance = sp.Variance(X, "covariance");
    double[][] correlation = sp.Variance(X, "correlation");

    np.PrintM(covariance);
    np.PrintM(correlation);

}
```


### Regression Coeffecients
![Equation](https://latex.codecogs.com/gif.latex?%5Cbeta%20%3D%20%28X%5ETX%29%5E%7B-1%7DX%5ETy)
```Java
public static void MultiVariableReg(){
    Matrix np = new Matrix();
    StatPack sp = new StatPack();
    double[][] X = {{1, 300, 298, 101},
                    {1, 320, 245, 102},
                    {1, 310, 233, 103},
                    {1, 290, 252, 108},
                    {1, 270, 253, 106},
                    {1, 320, 257, 140},
                    {1, 310, 254, 120},
                    {1, 315, 280, 101},
                    {1, 307, 260, 110},
                    {1, 312, 259, 107},
                    {1, 309, 251, 113}};

    double[] Yh = {20, 30, 50, 18, 23, 45, 66, 92, 84, 21, 55};

      double[][] beta = sp.Regression(X, Yh);

      np.PrintM(beta);

}

```
