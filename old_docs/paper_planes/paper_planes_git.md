# Paper plane version management

When people work together we need to manage versions.  Versions are the result of changes (improvements hopefully!) that people make.  

In this exercise we will explore a physical analogy of versions and learn the basic elements of managing versions with git.

# Set up

Create a group of 5 or 6 students.  Figure out the alphabetical order of your first names.

Roles:

1. The originator
2. Repository manager
3. Improver 1
4. Metadata manager

Materials:

1. Paper (~20 sheets)
2. Large Pink Postit 
3. Small postit notes: yellow, pink, blue.
4. 8 plastic trays

Arrange three tables in a vertical row, so there is space to stand between each of them.

The table on the left (facing the front) is the working area for **The originator**, they should sit at a seat.  This is where they will do their work.

The table in the middle is our **repository**. This is where we will store versions of the work over time.

The table on the right is where **Improver 1** will sit.

The *Repository manager* and the *Metadata manager* will stand at either end of the repository table.

## Step 1: Initial work

*Originator* shall fold an initial plane, but with only one wing.  (Fold down the center, then add the front folds to the center, then fold down a single wing).

![s1_1](images/s1_1.png)

To store this work in the repository we need to 

1. make a copy and place it on a plastic tray. 
2. Take a large pink postit and write a short descriptive note (e.g., "Just getting started") 
3. The tray is then handed to the *repository manager* who places it leftmost on the table.
4. The *metadata manager* attaches a small yellow postit marked "v1" (meaning version 1), to the tray in the repository **and to the tray on the Originators table**. 

![s1_2](images/s1_2.png)

Phew, all that hard work is now stored in the repository.

## Step 2: Complete the plane.

The *Originator* should work with their remaining plane and fold down the second wing.  Store this in the repository following the steps above.  

End point should have two trays in the repository, each with comments and a version number (v2). The tray on the originator's table is now also marked v2.

![s2_2](images/s2_2.png)

## Step 3: Improvement

**Improver 1** is now going to work.  They are sitting at the righthand table.

To get started they need to get a copy of the latest version from the repository.

The **Repository manager** gets a new tray and makes a copy of the v2 tray, the **metadata manager** should add the metadata postits.  This copy is handed to the **Improver 1** on their working table.![s3_1](images/s3_1.png)

Improver 1 should make an improvement by adding a small pink postit to the *left wing* of the plane. 

![s3_2](images/s3_2.png) 

Then they should put a copy into the repository following the steps above.

End point is that the repository now has v3 (with appropriate metadata), and the tray on the working table of Improver 1 is also marked v3. 

![s3_3](images/s3_3.png)

> The **Originator** might have heard about the new work in the repository, and they could now update their working directory to v3 and then take turns with **Improver 1** to contribute work. However, the world is not always as neat. Often contributors are working at the same time.

## Step 4: Concurrent work

**The Originator** is continuing their own work.  Notice they are working with v2.  They add a small blue post-it note to the *right wing*.

![s4](images/s4.png)

Follow the steps above to add this to the repository.  Place this copy to the right of v3 and mark it v4.

> Notice the problem?  **Originator** has overwritten the work that **Improver 1** added.  This happens often with shared files.

> What is needed to avoid this?  Somehow the repository needs to know that the incoming work is out of sync with the repository. We do this by keeping track of the spot that a working directory can slot into in the repository.

The **metadata manager** should take small yellow post-it notes and add a *Parent* tag to each version in the repository (and on the working tables).  The Parent for v1 is "null" (meaning empty). The Parent for v2 is v1.  This means that the repo looks like null <- v1 <- v2 <- v3 

## Step 5: Synchronization (no conflict)

With the parent tags in place we can try again. The new rule is that **repository manager** will only accept work if the working directory is up to date. v2 on the originators table has v1 as the parent. Once we make changes to this work we update the parent tag to say v2 (so that this work can only be checked in as v3).

When the originator tries to check in this work, the repository rejects it (because there is already something attached to v2, in the v3 slot).

In this situation the *originator* has to update from the repository.  The repository manager/metadata manager should make a copy of v3 and pass to the originator.  Now the originator has the repositories v3 (with a pink post-it on the left wing) and their proposed v3 (with a blue post-it on the right wing).

![s5_1](images/s5_1.png)

The system is able to automatically merge this work.  Simulate this by adding a pink post-it to the left wing of the proposed v3.  

![s5_2](images/s5_2.png)

Now Originator is able to check this work in and the repository will accept it as v4.  Do this now.

![s5_3](images/s5_3.png)

## Step 6: Synchronization (with conflict).

The system is not always able to automatically merge changes.  We will simulate this by discarding the combined v4 made in Step 5 from the repository, resetting to the end of Step 3.

This time, however, the originator places the blue post-it on the left wing (same place as the improver had placed the pink post-it.)

When they synchronize, the system identifies a conflict, which the Originator has to resolve.  

![s6_1](images/s6_1.png)

Note that they can do any work they want here, and check that in as the new v4.

![s6_1](images/s6_2.png)
