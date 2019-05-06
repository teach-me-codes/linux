### Installing Software Packages (Debian/Ubuntu)

- ```/etc/apt/sources.list``` : Stores the repository locations that apt uses to search for packages specific to your system
- ```apt-get``` : Package handling and installation utility for Debian-based distributions
  - Installs packages by name and includes dependent packages during install
- ```dpkg``` : Installs .deb package files on Debian-based systems
  - ```-i``` – Install as well as configure package
  - ```-r``` – Remove package
  - ```-configure```– Configures a package
  - ```-c```– List contents of a package
  -```-s``` – List status of package (installed or not)
-```apt-cache``` : Allows searching of named package or shows installed packages
  -  ```apt-cache pkgnames```– Show installed
  - ``` apt-cache search```– Search for named package
- ```dpkg-reconfigure``` : Reconfigure an already-installed package
- ```aptitude``` : High level package management interface for Debian-based distributions
