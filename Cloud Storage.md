#service #storage #files

A GCP service that allows users to persist [[Unstructured data]].

![[Pasted image 20250815134659.png]]

![[Pasted image 20250815134806.png]]

# Caveats

- All objects have a globally unique identifier
- All objects have a unique name
- All objects have a specific geographic location (from which the object will have less latency) 
- Objects **CANNOT** be modified, only versioned, if a user wants to make a change he'll have to create a new version 
- If bucket versioning is not enabled the user will create a new version and delete the current one

All file storage classes share the following features

![[Pasted image 20250815140827.png]]

# Types of file storage

![[Pasted image 20250815135808.png]]

- [[File storage]]
- [[Block storage]]
- [[Object storage]]

# File storage classes

File storage is billed taking into account the class that the storage is assigned to, the optimal class for a given file depends on the frecuency of the access to it.

![[Pasted image 20250815140512.png]]

- [[Standard storage]]
- [[Nearline storage]]
- [[Coldline storage]]
- [[Archive storage]]

# Lifecycle management

We can specify a lifecycle for files, meaning that whenever a set of conditions is met, we can trigger actions to the file, like for example
- We can configure the bucket to delete all files that are more than 365 days old.
- We can configure files to only persist the 3 most recent versions.