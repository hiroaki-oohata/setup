# setup
VScode�AGit�AGitHub�AUbuntu���g�p�����J�����ł���悤�A�Z�b�g�A�b�v���s���܂��傤�B


## Ubuntu�iLinux�j
�z�X�gOS�������Ȃ��悤�Q�X�gOS��p�ӂ��܂��B  
Linux�͊J�������ň��肵�Ă���A�l�X�ȃc�[�����p�ӂł���̂ő�ϕ֗��ł��B  
������@���Linux��������悤�ɂȂ�܂��傤�B  
(�C���X�g�[���Ɏ��Ԃ�������̂ł��ꂩ��n�߂܂�)  
### Windows
1. WSL2��L��������
�N������O��WSL2��L�������Ă����K�v������܂��B  
���ċN�����K�v�ɂȂ�܂��B  
�i�Q�l�jhttps://www.kagoya.jp/howto/it-glossary/develop/wsl2_linux/  
    1. Linux�C���X�g�[���O�̏������s��  
    1. WSL2�pLinux�J�[�l�����C���X�g�[������  
    1. WSL2������̃o�[�W�����ŗ��p�ł���悤�ɂ���  

2. MicrosoftStore���N������  
![MicrosoftStore](Images/MicrosoftStore.png)

3. Ubuntu�Ō�������  
Ubuntu 22.04.2 LTS �����肵�Ă��āA���p�҂������ł��B
![Ubuntu](Images/Ubuntu_Install.png)

4. �N������  
���[�U�[���A�p�X���[�h�����߂�悤�������B  
���K�����͂���B���������ʂ���Ă��܂�Ȃ��悤���ӁB  
������N���̓Z�b�g�A�b�v�Ɏ��Ԃ�������܂��B�i5�����x�H�j  
![Ubuntu](Images/Ubuntu2204-01.png)

5. Ubuntu��Vesion���m�F����  
```bash  
lsb_release -a
```  


### Mac
Ubuntu�����K�v�͖���������B�������B


## GitHub
1. �T�C���A�b�v  
�ȉ��̃y�[�W�փA�N�Z�X���ăA�J�E���g���쐬���܂��B  
�ڂ������Ƃ͕ʂ̃T�C�g���Q�Ƃ��Ȃ���i�߂Ă��������B  
�@�i�Q�l�jhttps://qiita.com/ayatokura/items/9eabb7ae20752e6dc79d

```bash
https://github.com/
```

2. �T�C���C��  
�T�C���C���ɐ������邩�m�F���܂��B  

3. �g�[�N���̔��s  
���|�W�g���̃N���[����v�b�V���ȂǁA�������ʂŃg�[�N���̓��͂����߂��܂��B  
�g�[�N���͍Ĕ��s�ł��܂����A�ʓ|�Ȃ̂Ŗ������Ȃ��悤�ɊǗ����܂��B  
���ڂ������Ƃ͕ʂ̃T�C�g���Q�Ƃ��Ȃ���i�߂Ă��������B  
�@�i�Q�l�jhttps://capybara-notebook.com/github_accesstoken/


## Git�iUbuntu�փC���X�g�[���j
���|�W�g�����N���[������Ȃǂ̑���Ɏg�p���܂��B
�z�X�gOS�ł͎g�p���Ȃ��̂�Ubuntu�ɓ���܂��B
1. �C���X�g�[��  
�܂���Ubuntu��ňȉ��̃R�}���h��ł��Ă݂܂��B
Version���Ԃ��Ă����炷�łɃC���X�g�[������Ă��܂��B
```bash
git version
```
- �����A�C���X�g�[������Ă��Ȃ���΁AUbuntu��ł��̃R�}���h�����s���邾���B  
�ƂĂ��ȒP�B  
(�O�̂��߁A���s���Ă����Ă��ǂ�)   

```bash
sudo apt update
sudo apt-get install git
```

2. �����ݒ�  
[GitHub](#github)�ō쐬�����A�J�E���g��o�^���܂��B  
```bash
git config --global user.name "yamada-taro"
git config --global user.email xxx@yahoo.co.jp
```

## VSCode(�z�X�gOS�փC���X�g�[��)
�l�X�Ȋg���@�\��������Ă���A����ЂƂŊJ���\�ȓ����J�����ł��B  
1. �C���X�g�[��  
�ȉ�����C���X�g�[�����擾���܂��B  
�C���X�g�[�������{�B
```bash
https://code.visualstudio.com/
```
2. VScode���N�����Ċg���@�\�𓱓�
- Japanese Language Pack for Visual Studio Code
- Remote-WSL
- Git Graph
- Git History
- Dev Containers
- Docker
- Bazel
- Draw.io Integration

## Docker
�����܂ōs���邩�킩��Ȃ��̂ŕ��u  

## Jenkins
1. WSL2(Ubuntu)���ňȉ��̃R�}���h�����ԂɎ��s
```
$ sudo apt -y install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
# JAVA
$ sudo apt -y install openjdk-8-jdk
$ sudo apt -y install openjdk-11-jre-headless
# Jenkins
$ wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add
$ sudo bash -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
$ sudo apt update
$ sudo apt install jenkins
# Update Firewall to enable Jenkins service
$ sudo ufw enable
$ sudo ufw allow 8080 # whatever port number you like
$ Check the status of your port:
$ sudo ufw status
# Run Jenkins server
$ sudo service jenkins start
# ���̌�AWinodws�u���E�U��http://localhost:8080/ ����Jenkins�ɃA�N�Z�X�ł���
# �ł��Ȃ��ꍇ�� Jenkins��WSL��power shell����`wsl.exe --shutdown` �ōċN�����Ă���ēxjenkins start���Ă݂�
# �����p�X���[�h�m�F
$ sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```
- �ȉ��̉�ʂ��o���OK  
![MicrosoftStore](Images/Jenkins_first.png)
- ��L�ɏ����p�X���[�h����͂���  

2. ���Ƀv���O�C���̃C���X�g�[���m�F��ʂ��\�������B  
�uInstall suggested plugins�v��I������B

3. �����I�Ƀv���O�C���̃_�E�����[�h���C���X�g�[�����n�܂�̂ŃC���X�g�[������������܂ő҂B  

4. ����Admin���[�U�쐬��ʂ��\�������̂ŕK�v��������͂���[Save and Continue]�{�^���������B  

# supplement
## �u�����`��ی삵����  
main�u�����`�֒���Push�ł��Ȃ��悤�ɕی삷����@  
https://zenn.dev/snowcait/articles/42bb6b56c806da



