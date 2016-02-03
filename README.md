# espresso-customThreadPool

Added code to two espresso-core classes so that we can register a thread name to be checked in addition to asyncTask threads when checking if the app being tests is currently idle. We use this so that espresso will wait for our network calls to finish before trying to perform a view action. 

##Changes to Espresso2.2.1

###Espresso.java

static void registerCustomThreadName(String name)
  -registers custom thread name, active threads with this name will have their states checked when asyncTask thread states are checked for idle (TERMINATED, BLOCKED or WAITING) before espresso performs a view action. 
  
###AsyncTaskPoolMonitor.java

void getThreadName()
  -get custom thread name if one has been registered in Espresso.java
  
boolean customThreadsIdle()
  -get custom thread name and check for idle threads, return false if active threads with registered name or true if there are not active threads with registered name
  
int getActive(String name)
  -returns number of active threads not currently in Terminated, Blocked, or Waiting state
  
  

