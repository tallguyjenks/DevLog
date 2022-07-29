
## The Difference Between Images and Containers

> Images are what you create when you run docker build; they’re stored in a container registry like the Docker Hub, and contain all the files and code to run an app. You can think of them like ISO files for a virtual machine operating system.
>
> Containers are created from images, and they’re like the actual virtual machine that runs the application. You might have multiple containers running in parallel off the same image. **Each container will have its own file system, optionally created with “volume mounts” that bind data from the host to the container.**

## Images stored locally

- **Linux:** `/var/lib/docker/`
- **Windows:** `C:\ProgramData\DockerDesktop`
- **macOS:** `~/Library/Containers/com.docker.docker/Data/vms/0/`

## Notes

- [[s.containers.docker.cmd.image.ls]]
- [[s.containers.docker.cmd.image.prune]]
- [[s.containers.docker.cmd.inspect]]
- [[s.containers.docker.tips-and-tricks.modify-container-filesystem]]
