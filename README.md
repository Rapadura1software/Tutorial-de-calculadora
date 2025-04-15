# Tutorial-de-calculadora
#Oi pessoal aqui esta o codigo da calculadora nao por intero mas uma parte 

from IPython.display import display
import ipywidgets as widgets
from IPython.display import clear_output
import time
from ipywidgets import HBox
from IPython.display import HTML
import math

def clean():
  clear_output(wait=False)
  time.sleep(0.5)
  clear_output(wait=True)

  

line = widgets.Textarea(
    value="",
    layout=widgets.Layout(width="600px")
)

def execute(b):
  global line
  print(eval(line.value))





def apaga(b):
  global line
  line.value = line.value[:-1]


button_apaga = widgets.Button(description="C:")
button_apaga.style.button_color = "green"
button_apaga.on_click(apaga)



button_execute = widgets.Button(description="=")
button_execute.style.button_color = "green"
button_execute.on_click(execute)


def number_an(b):
  global line
  line.value += "1"


button_an = widgets.Button(description="1")
button_an.style.button_color = "blue"
button_an.on_click(number_an)


def number_two(b):
  global line
  line.value += "2"


button_two = widgets.Button(description="2")
button_two.style.button_color = "blue"
button_two.on_click(number_two)





def func_plus(b):
  global line
  line.value += "+"


button_plus = widgets.Button(description="+")
button_plus.style.button_color = "red"
button_plus.on_click(func_plus)

def func_menos(b):
  global line
  line.value += "-"


button_menos = widgets.Button(description="-")
button_menos.style.button_color = "red"
button_menos.on_click(func_menos)


def func_vezes(b):
  global line
  line.value += "*"


button_vezes = widgets.Button(description="*")
button_vezes.style.button_color = "red"
button_vezes.on_click(func_vezes)

def func_div(b):
  global line
  line.value += "/"


button_div = widgets.Button(description="/")
button_div.style.button_color = "red"
button_div.on_click(func_div)

def calculadora(b):
  clean()
  display(line)
  display(HBox([button_an,button_two]))
  display(HBox([button_plus,button_menos,button_vezes]))
  display(button_div)
  display(button_execute)
  display(button_apaga)


button_calculadora = widgets.Button(description="calculadora")
button_calculadora.style.button_color = "red"
button_calculadora.on_click(calculadora)

display(button_calculadora)
