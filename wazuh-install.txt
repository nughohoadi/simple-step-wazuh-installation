Linux APT :
  1. Install the following packages if missing.\
      apt-get install gnupg apt-transport-https
  2. Install the GPG key.
      curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | gpg --no-default-keyring --keyring gnupg-ring:/usr/share/keyrings/wazuh.gpg --import && chmod 644 /usr/share/keyrings/wazuh.gpg
  3. Add the repository.
      echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list
      note : https://packages.wazuh.com/4.x/apt/ --> update this with current release
  4. Update the packages information.
      apt-get update

Linux YUM :
  1. Import the GPG key.
      rpm --import https://packages.wazuh.com/key/GPG-KEY-WAZUH
  2. Add the repository.
      echo -e '[wazuh]\ngpgcheck=1\ngpgkey=https://packages.wazuh.com/key/GPG-KEY-WAZUH\nenabled=1\nname=EL-$releasever - Wazuh\nbaseurl=https://packages.wazuh.com/4.x/yum/\nprotect=1' | tee /etc/yum.repos.d/wazuh.repo
      note : https://packages.wazuh.com/4.x/yum/ --> update this with current release

Download and run wazuh simple installation : 
  curl -sO https://packages.wazuh.com/4.8/wazuh-install.sh && sudo bash ./wazuh-install.sh -a -i
  note : https://packages.wazuh.com/4.8/ --> update this with current release
