## Haskell
	- Use System.Random to get random number in Haskell.
	-
	  ```haskell
	  >> import System.Random
	  >> randomIO :: IO Int               -- generate random integer
	  -7169119540275222050
	  >> randomIO :: IO Double            -- generate random fp
	  0.5512860729201712
	  >> randomRIO (1, 10) :: IO Int      -- generate random integer range [1, 10]
	  6
	  ```
	- Use System.IO.Unsafe to extract number from IO wrap.
	-
	  ```haskell
	  main = do
	      print (unsafePerformIO randomIO :: Int)
	  ```
- ## Rust
- ## C/Cpp
	-
	  ```c++
	  #include <ctime>
	  #include <cstdlib>
	  
	  int main() {
	      srand((unsigned)time(NULL));            // Use system time as random seed
	      int i1 = rand();                        // generate random integer
	      int i2 = rand() % MAX;                  // generate random integer range [0, MAX)
	      double d = rand() % double(RAND_MAX);   // generate random fp range [0, 1)
	  }
	  ```
- ## Java
	- Use java.util.Random
		-
		  ```java
		  import java.util.Random;
		  
		  Random r = new Random();        // get a instance of java.util.random
		  int i1 = r.nextInt();           // generate random integer
		  int i2 = r.nextInt(3);          // generate random integer range [0, 3)
		  double d1 = r.nextDouble();     // generate random fp
		  double d2 = r.nextDouble(1.0);  // generate random fp range [0, 1)
		  ```
	- Use Math.random()
		-
		  ``` java
		  double dr1 = Math.random();               // generate random fp range [0, 1)
		  double dr2 = Math.random()*(n-m+1)+m;     // generate random fp range [m, n)
		  int ir = (int)(Math.random()*(n-m+1)+m);  // generate random integer range [m, n)
		  ```