# espresso-customThreadPool

##Changes to Espresso2.2.1

###Espresso.java

static void registerCustomThreadName(String name)
  -registers custom thread name, active threads with this name will have their states checked when asyncTask thread states are checked for idle (TERMINATED, BLOCKED or WAITING)
  
###AsyncTaskPoolMonitor.java

void getThreadName()
  -get custom thread name if one has been registered in Espresso.java
  
boolean customThreadsIdle()
  -get custom thread name and check for idle threads, return false if active threads with registered name or true if there are not active threads with registered name
  
int getActive(String name)
  -returns number of active threads not currently in Terminated, Blocked, or Waiting state
  
  
