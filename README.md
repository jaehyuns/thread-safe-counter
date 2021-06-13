# thread-safe-
Locking with a semaphore took about 30 times longer than locking with a mutex. The semaphore took about 3 seconds and the mutex took about 0.1 seconds. The reason is that a mutex is simply locked/unlocked, whereas a semaphore changes the lock value around its critical section as it continuously exits or enters. And I think that it takes more time than the mutex because it takes a long time to come in after checking the changed value and change the number.

time input 1000000
semaphore:real	0m3.732s
	  user	0m0.441s
          sys	0m4.924s

mutex:real  0m0.171s
      user  0m0.182s
      sys   0m0.157s
