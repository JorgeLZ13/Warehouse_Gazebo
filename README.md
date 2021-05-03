
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
* ROS Noetic
* Gazebo
* Rviz

## Instalação 
Para instalar o robô coloque os pacotes <code> robot_descriptoin</code> e <code> robot_control</code> em seguida faça o catkin_make do seu workspace.


## Executando a Simulação

### Como executar o ambiente de simulação
Para executar o ambiente de simulação utilize o comando:

<p>
  <code>roslaunch robot_description spawn.launch</code>
</p>

### Como executar o controle do robô

Para executar o controle do robô você utiliza o comando:
<p>
<code>roslaunch robot_control control.launch</code>
</p>

### Como executar o Rviz

Para executar o controle do robô você utiliza o comando:
<p>
<code>roslaunch robot_control control.launch</code>
</p>

## Autor
