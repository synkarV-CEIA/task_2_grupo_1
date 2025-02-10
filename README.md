# Task 2 - Teste Teleop-twist-keyboard 

## Grupo 1 - Davi, Fernanda, Gabriel, Naomi e Raissa

### Setup necessário: Já ter o ROS 1 configurado na sua máquina e ter acesso a sala PixelLab 253.

Para acessar a sala é necessário ter biometria, tendo em vista que a secretaria do INF não possui uma chave reserva. A secretária mencionou a existência de um aplicativo que liberaria acesso remoto, mas não deu mais informações. O professor responsável pelo cadastro de biometria é o Prof. Gustavo Laureano, mas no momento de escrita desta documentação (fev-2025) ele se encontra de férias.

## Sobre a base CEIA:
+ Necessário carregar a base por aproximadamente 2h antes de usar. O carregador possui um LED que fica verde quando a bateria está carregada.

+ Conecte o computador no cabo de rede (RJ45) e realize o procedimento de configuração da conexão cabeada manualmente ao IP do robô (10.0.0.10 ou 10.0.0.1)

+ Referencie o source.bash nos três terminais que terá que abrir (source /opt/ros/<distro>/setup.bash source ou devel/setup.bash se usar catkin)

+ Inicie o núcleo roscore: $ roscore

+ Noutro terminal, inicie o nó rosserial teleop: $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py _cmd_vel:=/topico_da_base (essa parte do comando é importante apenas se o tópico _cmd_vel for renomeado na base utilizada)

+ No caso de ter sido renomeado, utilizar $ rostopic list para verificar o nome utilizado

+ Para os tópicos das câmeras,
 
  $ sudo apt-get install ros-noetic-realsense2-camera 

  #### ou
 
  $ cd ~/catkin_ws/src

  $ git clone https://github.com/IntelRealSense/realsense-ros.git
 
  $ cd ~/catkin_ws
 
  $ catkin_make

  $ source devel/setup.bash // a diferença é somente o ambiente catkin

+ Finalmente, $ roslaunch realsense2_camera rs_camera.launch
  
+ Iniciar também o RQT Image view

Pode-se criar um launcher .sh com os comandos de source e que iniciam os nós ROS para facilitar o trabalho.
[Launcher criado](https://drive.google.com/drive/folders/1BAry6uHipLiYjNYYD26rHMIHCejw9lDy?usp=sharing)
