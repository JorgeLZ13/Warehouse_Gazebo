
<p align="middle">
<img src="https://github.com/JorgeLZ13/Warehouse_Gazebo/blob/main/Logo%20simulador%20do%20rob%C3%B4.png"  height="243" width="541"/>
</p>

<h1 align="center">Simulação de Robô para Armazém de Distribuição</h1>


## Descrição
Esse projeto tem o intuito de simular um armazém de distribuição através do gazebo, controlando um robô através do teclado e movimentando suas prateleiras, a simulação conta com diversos recursos de sensores como odometria, IMU, laser e câmera.

>Status: 🚧 Em andamento 🚧


## Demonstração da aplicação

Tabela de conteúdos
=================
<!--ts-->
   * [Descrição](#Descrição)
   * [Tabela de Conteudo](#Tabela-de-conteúdos)
   * [Pré-requisitos](#Pré-requisitos)
   * [Instalação](#Instalação)
   * [Executando a simulação](#Executando-a-Simulação)
      * [Como executar o ambiente de simulação](#Como-executar-o-ambiente-de-simulação)
      * [Como executar o controle do robô](#Como-executar-o-controle-do-robô)
      * [Como executar o Rviz](#Como-executar-o-Rviz)
   
   * [Tecnologias](#Tecnologias)
   * [Autor](#Autor)
<!--te-->

## Pré-requisitos 
* Ubuntu 20.04
* <a href="http://wiki.ros.org/noetic/Installation/Ubuntu"> ROS Noetic</a>
* <a href="http://gazebosim.org/tutorials?tut=install_ubuntu"> Gazebo</a>
* <a href="http://gazebosim.org/tutorials?tut=ros_installing&cat=connect_ros"> Gazebo ROS Packages</a>
* <a href="http://wiki.ros.org/rviz/UserGuide"> Rviz</a>
* <a href="https://docs.python-guide.org/starting/install3/linux/"> Python 3.8</a>
* <a href="http://wiki.ros.org/ros_control"> ROS Control</a>

## Instalação 
Em seu Workspace dentro da pasta <code>src</code> coloque os pacotes <code>robot_description</code> e <code>robot_control</code> 
em seguida faça o <code>catkin_make</code> para instalar os pacotes.


## Executando a Simulação

### Como executar o ambiente de simulação
Agora você pode usar o seguinte comando para iniciar o ambiente(use estes comandos dentro do seu workspace):

<p>
  <code> source ./devel/setup.bash </code> <br />
  <code>roslaunch robot_description spawn.launch</code>
</p>

Se tudo der certo você verá o laser_bot dentro no meio da warehouse.

### Como executar o controle do robô
Se você quiser mover o robô pela warehouse use os seguintes comandos:

<p>
    <code> source ./devel/setup.bash </code> <br />
    <code>roslaunch robot_control control.launch</code>
</p>

Caso queira mover a bandeja utilize o comando abaixo em outro terminal com <code>"data: 1"</code> para subir e <code>"data: 0"</code> para descer:

<p>
    <code>rostopic pub -1 /my_robot/joint1_position_controller/command std_msgs/Float64 "data: 0"</code>
</p>

### Como executar o Rviz
Para utilizar os sensores como <code>câmera</code> e <code>laser</code> criamos um atalho através do Rviz:

<p>
    <code> source ./devel/setup.bash </code> <br />
    <code>roslaunch robot_description rviz.launch</code>
</p>

## Autor
