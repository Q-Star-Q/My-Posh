# My-Posh
the configuration of my **PowerShell** - posh on Windows Terminal (Windows 10) .  

- **1. Configure Windows Terminal**  
  - **Appearance**  
    - Color scheme: One Half Dark  
    - Font face: Hack NF  
  - **Acrylic** 
    - Enable acrylic: on  
    - Acrylic opacity: 50%  
  ***If you don't have a Nerd font, switch to https://www.nerdfonts.com***
    
- **2. Install PowerShell** 
  - download **PowerShell** at Microsoft Store. 
  - set default shell as **PowerShell** (***NOT*** *Windows PowerShell*) 
  
- **3. change the terminal background color**  
  - Duplicate the "One Half Dark" theme and rename it (edited by VScode)  
  - change the new theme background color **"#282C34"** to **"#001B26"**  
  - change the **Color scheme** to your new theme color : ) such as one Half Dark(modded)  

- **4. Install the Command-line installer: Scoop**  
  - read https://scoop.sh , copy  `iwr -useb get.scoop.sh | iex`  
  - execute `iwr -useb get.scoop.sh | iex` and wait for finished.  
  - execute `scoop install curl sudo jq`  

- **5. Install Git for Windows**  
  - execute `winget install -e --id Git.Git` and wait for finished.  
  - execute the **Git Setup**  

- **6. Install Neovim**  
  - execute `scoop install neovim gcc`  
  - execute `nvim --version` to make sure your current neovim version.  

- **7. Make your user profile and set command aliases**  
  - execute `mkdir .config/powershell` to create configuration of your powershell.  
  - use neovim to edit it, such as `nvim .config/powershell/user_profile.ps1` | you can also use VScode to complete this process.  
  - (Neovim) input key `i` to insert your codes. For example:  
  ```
  # Alias 
  Set-Alias vim nvim 
  Set_Alias ll ls 
  Set-Alias g git 
  Set-Alias grep findstr 
  Set-Alias tig 'C:\Program Files\Git\usr\bin\tig.exe' 
  Set-Alias less 'C:\Program Files\Git\usr\bin\less.exe' 
  ```
  - input key `esc` to quit `INSERT` mode. 
  - input `:wq` to save and quit currently. 
  - execute `nvim $PROFILE.CurrentUserCurrentHost` to use neovim to edit the file (C:\Documents\PowerShell\Microsoft.PowerShell_profile.ps1)
  - (Neovim) input key `i` to insert.
  ```
  . $env:USERPROFILE\.config\powershell\user_profile.ps1

  ```
  - input `esc` to quit `INSERT`.  
  - input `:wqa` to save all and quit currently.  
  ***You can open another session and make sure the aliases are working. such as `ll | less`***  

**8. Install Oh-My-Posh**  
  - execute `Install-Module posh-git -Scope CurrentUser -Force`  
  - execute `Install-Module oh-my-posh -Scope CurrentUser -Force`  
  - edit `user_profile.ps1`  
  ```
  # Prompt
  Import-Module posh-git
  Import-Module oh-my-posh
  Set-PoshPrompt Paradox 
  # Alias 
  Set-Alias vim nvim 
  Set_Alias ll ls 
  Set-Alias g git 
  Set-Alias grep findstr 
  Set-Alias tig 'C:\Program Files\Git\usr\bin\tig.exe' 
  Set-Alias less 'C:\Program Files\Git\usr\bin\less.exe' 
  ```
  - input `esc` and `:wq` .  
  - wait for downloads finished.  
  
