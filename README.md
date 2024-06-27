## How to Create a Desktop Icon to Run `gui5.py` on Jetson Nano

Jetson Nano의 바탕화면에 아이콘을 만들어서 클릭 시 GUI 프로그램을 실행하도록 설정할 수 있습니다. 이를 위해 .desktop 파일을 생성하고, 해당 파일을 바탕화면에 배치하여 설정합니다. 다음 단계로 진행해보겠습니다:

### Steps

1. **스크립트 파일 생성:**:
   먼저, gui5.py를 실행하는 스크립트 파일을 생성합니다. 예를 들어 run_gui.sh라는 이름으로 만듭니다.

   ```sh
   #!/bin/bash
   source /home/sensor/project/paddle3.7_copy/bin/activate
   cd /home/sensor/hynux/gui
   python3 gui5.py
   ```

2. **스크립트 파일에 실행 권한 부여:**:
   스크립트 파일에 실행 권한을 부여합니다. 터미널을 열고 다음 명령어를 입력하세요.

   ```sh
   chmod +x /home/sensor/run_gui.sh
   ```

3. **.desktop 파일 생성:**:
   바탕화면에 실행 아이콘을 만들기 위해 .desktop 파일을 생성합니다. 예를 들어 run_gui.desktop 파일을 만듭니다.

   ```desktop
    [Desktop Entry]
    Name=Run GUI
    Comment=Run GUI Application
    Exec=/home/sensor/run_gui.sh
    Icon=utilities-terminal
    Terminal=false
    Type=Application
   ```

4. **바탕화면에 .desktop 파일 배치:**:
   run_gui.desktop 파일을 바탕화면에 복사하거나 이동합니다.

   ```sh
   cp /home/sensor/run_gui.desktop /home/sensor/Desktop/
   ```

5. **실행 권한 부여:**:
   바탕화면에 복사한 .desktop 파일에 실행 권한을 부여합니다.
   ```sh
   chmod +x /home/sensor/Desktop/run_gui.desktop
   ```

위의 단계를 완료하면, 바탕화면에 "Run GUI" 아이콘이 생성될 것이고, 이를 클릭하면 터미널 없이 gui5.py 파일이 실행될 것입니다.
