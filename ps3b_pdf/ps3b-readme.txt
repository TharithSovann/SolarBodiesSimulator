/**********************************************************************
 *  N-Body Simulation ps3b-readme.txt template
 **********************************************************************/

Name: Tharith Sovann (Partner: Joseph Calles)
Hours to complete assignment: 10 hours

/**********************************************************************
 *  Briefly discuss the assignment itself and what you accomplished.
 **********************************************************************/
Building upon last week's ps3a, I implement the force, acceleration, and velocity of the
bodies which in turn would affect their positions. As a result, the planets are pictured in different positions which makes them appear to be moving. Their new positions are calculated and set very quickly so they do look like they are moving. Through some basic physics laws, we calculated the Force, then accelration, then velocity and position (in terms of x and y axis).

  /**********************************************************************
 *  Discuss one or more key algorithms, data structures, or 
 *  OO designs that were central to the assignment.
 **********************************************************************/
The only algorithms can be found in my functions used to calculate the force, acceleration,
velocity and position through basic math and physics formulas. I used unique_ptr and shared_ptr. I used unique_ptr to point to Body objects. Each of these unique_ptr are in a vector. So I have a vector of qunie_ptr that points to Body objects. I also used shared_ptr, pointing to doubles, to hold the universe radius and the G (6.67e-10).

/**********************************************************************
 *  Briefly explain the workings of the features you implemented.
 *  Describe if and how do you used the smart pointers 
 *  Include code excerpts.
 **********************************************************************/
After declaring a vector of unique_ptr that points to Body objects.
  std::vector<unique_ptr<Body>> bodies;
I fill in it's details from the planets.txt file through my overridden insertion operator. That is all from ps3a however. In ps3b, I created separate functions to calculate the force, acceleration, velocity, and position in terms of x and y. I used physics formulas such as F = (GM1M2)/(r^2) to get my overall force and used that to find my Force components in the x and y direction. To get the acceleration, I simply divide the force by the mass. To get the new velocity, I add the current velocity to (delta_time * acceleration). Now that we got velocity, we can get the new position. The new position will be the current position plus (delta_time * velocity). This shows the displacement after the amount of time. Of course, I calculated this for each x andy component. Also, I implemented the program to take in two more command-line arguments. The Total time for the program to run and delta time. The program will run until the current time (which increases by delta time for every step called) is more or equals to total time.Since G is constant I used a shared_ptr for it: shared_ptr<double> _big_G; This creates a chared_ptr pointing to a double. Since the gravitational force will always be there no matter if I delete it, it makes sense to be a shared_ptr.

/**********************************************************************
 *  List whatever help (if any) you received from the instructor,
 *  classmates, or anyone else.
 **********************************************************************/
I had a lot of help from the SFML library, the PDF, and my partner (Joseph).

/**********************************************************************
 *  Describe any serious problems you encountered.                    
 **********************************************************************/
I had a lot of problems in my math which resulted in the planets sometimes falling straight down to getting flung off the screen. Slowly I fixed the problem one by one by outputting the body's information and seeing what is being calculated wrong.

/**********************************************************************
 *  List any other comments here.                                     
 **********************************************************************/
This was a very fun project, the result was well worth the effort. I also did the elapsed time and sound exta credit.
