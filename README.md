![Preview](me.png)

# Terminal Customization with Oh-My-Posh on Windows

Customizing your Windows terminal using Oh-My-Posh can greatly enhance your command line experience. Follow these steps to get started:

1. **Installation**

   a. Install Oh-My-Posh using Winget:

   ```powershell
   winget install JanDeDobbeleer.OhMyPosh -s winget
   ```

   b. Alternatively, you can install it manually:

   ```powershell
   Set-ExecutionPolicy Bypass -Scope Process -Force; Invoke-Expression ((New-Object System.Net.WebClient).DownloadString('https://ohmyposh.dev/install.ps1'))
   ```

   c. Verify the installation by running:

   ```powershell
   oh-my-posh.exe
   ```

2. **Install Nerd Fonts**

   Visit [NerdFonts](https://www.nerdfonts.com/) and download your preferred Nerd Font. For example, you can download 'Hack Nerd-Font'.

3. **Create a PowerShell Profile**

   Run the following command to create a PowerShell profile:

   ```powershell
   echo 'test string' > $PROFILE
   ```

4. **Configure Themes**

   a. Open the PowerShell profile in Visual Studio Code:

   ```powershell
   code $PROFILE
   ```

   b. Add the following command to initialize and set a theme (modify as desired):

   ```powershell
   oh-my-posh --init --shell pwsh --config https://raw.githubusercontent.com/JanDeDobbeleer/oh-my-posh/v$(oh-my-posh --version)/themes/jandedobbeleer.omp.json | Invoke-Expression
   ```

5. **Additional Customization**

   a. **Folder Icons** - Install 'terminal-icons':

   ```powershell
   Install-Module -Name Terminal-Icons
   ```

   b. **History Command Enhancements** - Install 'PSReadLine':

   ```powershell
   Install-Module -Name PSReadLine -AllowPrerelease
   ```

6. **Import Modules**

   Add the following lines to your PowerShell profile:

   ```powershell
   Import-Module -Name Terminal-Icons
   Import-Module -Name PSReadLine
   Set-PSReadLineOption -PredictionSource History
   Set-PSReadLineOption -PredictionViewStyle ListView
   Set-PSReadLineOption -EditMode Windows
   ```
