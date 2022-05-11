# aur-installer

### This is a simple script to update/install a given set of packages from AUR (fallsback to pacman if package not available on AUR)

##Usage
`aur-installer package1 package2 ...`
#### OR
`somecommand-to-get-package-names | aur-installer`

###Usage with pamac
This is sort of why I felt compelled to make this utility. Pamac would fail the entire system update process if one package fails to build.
`aur-installer $(pamac checkupdates 2>&1 | tail -n +2 | awk '{print $1}' | awk '{print}' ORS=' ')`
#### OR
`pamac checkupdates 2>&1 | tail -n +2 | awk '{print $1}' | aur-installer`