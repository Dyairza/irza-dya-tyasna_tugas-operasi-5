
## 1. Execute All Profiles

1. **Display Profile Message**  
   Edit `/etc/profile` and display the following message:  
   ```bash
   echo "Profile dari /etc/profile"
   ```  
   ![Image 1](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/1.png)

2. **Edit Profiles**  
   Assuming your username is `stD02001`, edit the following profiles:  
   - `/home/stD02001/.bash_profile`
   - `/home/stD02001/.bash_login`
   - `/home/stD02001/.bashrc`
   - `/home/mahasiswa/.profile`  

   Replace `mahasiswa` with your username and add the echo message, e.g., in `.bash_profile`:  
   ```bash
   echo "Profile dari .bash_profile"
   ```  
   Repeat this for the other files, adjusting the file names.  
   ![Images](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/2.png)

3. **Substitute User and Exit**  
   - Substitute to the user `mahasiswa`:  
     ```bash
     $ su mahasiswa
     $ exit
     ```
   - Use the `-` option:  
     ```bash
     $ su - mahasiswa
     $ exit
     ```  
   - **Explain the difference between both commands.**  
   ![Image](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/10.png)

## 2. Customize Prompt String (PS)

1. **Change PS1 in `.bash_profile`**  
   Edit the file to change PS1 and export it:  
   ```bash
   PS1="> "
   export PS1
   ```
2. **Experiment with PS1**  
   Test the following prompt strings:  
   ```bash
   PS1="\! > "  # Example: 69 >
   PS1="\d > "  # Example: Mon Sep 23 >
   PS1="\t > "  # Example: 10:10:20 >
   PS1="Saya=\u > "  # Example: Saya=mahasiswa >
   PS1="\w > "  # Example: ~ >
   PS1="\h > "  # Example: hostname >
   ```  
   ![Image](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/12.png)

## 3. Logout Message

1. **Edit `.bash_logout`**  
   Display a message and delay for 5 seconds before clearing the screen:  
   ```bash
   echo "Terima kasih atas sesi yang diberikan"
   sleep 5
   clear
   ```  
   ![Image](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/13.png)

## 4. Bash Scripts

1. **Create Scripts**  
   Create the following scripts:
   - `p1.sh`:  
     ```bash
     #! /bin/bash
     echo "Program p1"
     ls -l
     ```
   - `p2.sh`:  
     ```bash
     #! /bin/bash
     echo "Program p2"
     who
     ```
   - `p3.sh`:  
     ```bash
     #! /bin/bash
     echo "Program p3"
     ps x
     ```

2. **Run Scripts**  
   Execute scripts using different combinations:  
   ```bash
   $ ./p1.sh ; ./p3.sh ; ./p2.sh
   $ ./p1.sh &
   $ ./p2.sh & ./p3.sh &
   $ (./p1.sh ; ./p3.sh) &
   ```  
   ![Images](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/20.png)

## 5. Jobs

1. **Loop Script (`pwaktu.sh`)**  
   Create a script that saves the date and time every 10 seconds:  
   ```bash
   #!/bin/bash
   while [ true ]; do
     date >> hasil
     sleep 10
   done
   ```
2. **Run as Background**  
   Run the loop and a `find` command in the background:  
   ```bash
   $ jobs
   $ find / -print > files 2>/dev/null &
   $ jobs
   ```
3. **Move Jobs to Foreground/Background**  
   ```bash
   $ fg %1  # Bring job 1 to foreground
   $ bg  # Move it back to background
   ```
4. **Stop Background Program**  
   ```bash
   $ ps x
   $ kill [PID]
   ```  
   ![Images](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/26.png)

## 6. History

1. **Change `HISTSIZE`**  
   Set `HISTSIZE` to 20:  
   ```bash
   $ HISTSIZE=20
   $ h
   ```
2. **Use History Commands**  
   - Execute command from 5 steps ago:  
     ```bash
     $ !-5
     ```
   - Repeat the last command:  
     ```bash
     $ !!
     ```
   - Navigate through history using `^P` and `^N`.
   - Execute command number 150:  
     ```bash
     $ !150
     ```
   - Repeat command starting with `ls`:  
     ```bash
     $ !ls
     ```  
   ![Images](https://github.com/Dyairza/irza-dya-tyasna_tugas-operasi-5/blob/main/31.png)
