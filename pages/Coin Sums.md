id:: : 61109ade-41bd-4504-afd3-306259e6361e
from:: Euler Project
identity:: 31

-
  ``` haskell
  count :: Int -> [Int] -> Int
  count 0 _ = 1
  count _ [] = 0
  count x y@(yh:ys)
    | x < 0 = 0
    | otherwise = count x ys + count (x - yh) y
  
  main = do
    print $ count 200 [1, 2, 5, 10, 20, 50, 100, 200]
  ```