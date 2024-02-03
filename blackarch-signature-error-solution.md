# BlackArch Signature Error Solution

If you insttall BlackArch top of ArchLinux they will be getting certificate error like this.

![image](https://github.com/waspthebughunter/notlarim/assets/100480448/2b731f3d-4bea-4907-a689-85de56edff09)

At this stage you must edit pacman.conf.

# Solution
1. Open pacman.conf with sudo rights.
  - ```bash
    sudo nano /etc/pacman.conf
    ```

2. Find BlackArch repository.
  - ![image](https://github.com/waspthebughunter/notlarim/assets/100480448/ee955934-a891-4706-8b80-49f7455202cd)

3. Add this text `SigLevel = TrustAll` and save & exit.
  - ![image](https://github.com/waspthebughunter/notlarim/assets/100480448/ca7171ac-b3d8-469d-9857-5b55d0b9db40)

4. Update.
  - ![image](https://github.com/waspthebughunter/notlarim/assets/100480448/e0b0f997-602f-4b27-b923-b093f3af0a54)


