**Histogram equalization** increases the global contrast of the image by distributing its intensity level. It's constructed as follows:

1. **First, create a grayscale image.**

   <img width="182" alt="image" src="https://user-images.githubusercontent.com/57295556/164735137-df349aac-e6ad-4ebf-80e1-bf405f250976.png">

2. **Convert into numpy array.**
3. **Create original image’s histogram.**

   *Image’s original intensity distribution:*    
   
   <img width="205" alt="image" src="https://user-images.githubusercontent.com/57295556/164735314-752823eb-0999-42d1-ad4e-8e1a86fed02b.png">


   *Image’s original histogram distribution:*
   
   <img width="197" alt="image" src="https://user-images.githubusercontent.com/57295556/164735472-4b994948-8973-44f0-815b-e7bc6f34cfd1.png">

4.	**Make a map from old colors to new ones and apply the mapping to create a new equalized image.**

    <img width="163" alt="image" src="https://user-images.githubusercontent.com/57295556/164735655-53878f05-bf08-48e2-9d96-14e75dd35aba.png">

5. **Calculate the histogram cumulative distribution for the new image.**

    <img width="248" alt="image" src="https://user-images.githubusercontent.com/57295556/164735711-f07830f5-01de-4f6b-8815-0a9a222d3ed3.png">

   Above image shows the original and equalized histogram in the same plot. As observed, changes are significant. We can conclude that histogram      equalization helped the image to stretch out the frequently used intensity values.
