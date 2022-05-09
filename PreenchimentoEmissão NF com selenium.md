```python
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.common.by import By

servico = Service(ChromeDriverManager().install())
navegador = webdriver.Chrome(service = servico)
```

    
    
    ====== WebDriver manager ======
    Current google-chrome version is 101.0.4951
    Get LATEST chromedriver version for 101.0.4951 google-chrome
    Driver [C:\Users\Admin\.wdm\drivers\chromedriver\win32\101.0.4951.41\chromedriver.exe] found in cache
    


```python
# abrir arquivo
import os
caminho = os.getcwd()
arquivo = caminho + r'\login.html'
navegador.get(arquivo)

```


```python
#Preencher login , senha
navegador.find_element(By.XPATH,'/html/body/div/form/input[1]').send_keys('William Irassochio')
navegador.find_element(By.XPATH,'/html/body/div/form/input[2]').send_keys('00000')

#Clicar login
navegador.find_element(By.XPATH,'/html/body/div/form/button').click()
```


```python
# Preencher formulario
#Razao social
navegador.find_element(By.NAME,'nome').send_keys('Irassochio')
#Endereco
navegador.find_element(By.NAME,'endereco').send_keys('Rua Parobé')
#Bairro
navegador.find_element(By.NAME,'bairro').send_keys('Centro')
#Municipio
navegador.find_element(By.NAME,'municipio').send_keys('Parobé')
#CEP
navegador.find_element(By.NAME,'cep').send_keys('12345678')
#UF
navegador.find_element(By.NAME,'uf').send_keys('RS')
#CNPJ
navegador.find_element(By.NAME,'cnpj').send_keys('1234567890')
#Inscricao
navegador.find_element(By.NAME,'inscricao').send_keys('12345678')
#Descricao
navegador.find_element(By.NAME,'descricao').send_keys('Produtos digitais')
#Quantidade
navegador.find_element(By.NAME,'quantidade').send_keys('1')
#Vlr unt
navegador.find_element(By.NAME,'valor_unitario').send_keys('10')
#Vlr Total
navegador.find_element(By.NAME,'total').send_keys('10')
```


```python
#Clicar botão Emitir nota
navegador.find_element(By.CLASS_NAME,'registerbtn').click()
```


```python

```
