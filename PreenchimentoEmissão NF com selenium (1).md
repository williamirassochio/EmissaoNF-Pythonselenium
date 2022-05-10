```python
from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.common.by import By

options = webdriver.ChromeOptions()
options.add_experimental_option("prefs", {
  "download.default_directory": r"C:\Users\Admin\downloads",
  "download.prompt_for_download": False,
  "download.directory_upgrade": True,
  "safebrowsing.enabled": True
})
servico = Service(ChromeDriverManager().install())
navegador = webdriver.Chrome(service = servico, options = options)
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
#importar base de clientes
import pandas as pd

tabela = pd.read_excel('NotasEmitir.xlsx')
display(tabela)

```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cliente</th>
      <th>CPF/CNPJ</th>
      <th>CEP</th>
      <th>Endereço</th>
      <th>Bairro</th>
      <th>Municipio</th>
      <th>UF</th>
      <th>Inscricao Estadual</th>
      <th>Descrição</th>
      <th>Quantidade</th>
      <th>Valor Unitario</th>
      <th>Valor Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Valentina Márcia Melissa da Cunha</td>
      <td>25379574076</td>
      <td>73402036</td>
      <td>Módulo Módulo 12</td>
      <td>Estância Mestre D'Armas V (Planaltina)</td>
      <td>Brasília</td>
      <td>DF</td>
      <td>213873</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>3</td>
      <td>273</td>
      <td>819</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Lara Benedita Josefa Drumond</td>
      <td>30227643160</td>
      <td>78730170</td>
      <td>Avenida Manoel de Araújo Piau</td>
      <td>Jardim Belo Panorama</td>
      <td>Rondonópolis</td>
      <td>MT</td>
      <td>194139</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>6</td>
      <td>730</td>
      <td>4380</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Silvana Melissa da Paz</td>
      <td>36636402806</td>
      <td>69308220</td>
      <td>Rua Madre Rosa</td>
      <td>Treze de Setembro</td>
      <td>Boa Vista</td>
      <td>RR</td>
      <td>203703</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>2</td>
      <td>389</td>
      <td>778</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Pietro Diego César Monteiro</td>
      <td>51701896486</td>
      <td>60182541</td>
      <td>Rua Sousa Bandeira</td>
      <td>Antônio Diogo</td>
      <td>Fortaleza</td>
      <td>CE</td>
      <td>326342</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>2</td>
      <td>652</td>
      <td>1304</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Tomás Gabriel Alves</td>
      <td>59992546980</td>
      <td>96830690</td>
      <td>Rua Capitão Francisco Cândido de Castro Menezes</td>
      <td>Aliança</td>
      <td>Santa Cruz do Sul</td>
      <td>RS</td>
      <td>549783</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>9</td>
      <td>533</td>
      <td>4797</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Rodrigo Manoel Nunes</td>
      <td>83916914545</td>
      <td>60345640</td>
      <td>Travessa João Rodrigues</td>
      <td>Vila Velha</td>
      <td>Fortaleza</td>
      <td>CE</td>
      <td>554821</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>6</td>
      <td>440</td>
      <td>2640</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Lúcia Allana Pires</td>
      <td>74029234607</td>
      <td>68909823</td>
      <td>Avenida Hermes Monteiro da Silva</td>
      <td>Novo Horizonte</td>
      <td>Macapá</td>
      <td>AP</td>
      <td>396745</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>8</td>
      <td>466</td>
      <td>3728</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Kaique Lucca Mendes</td>
      <td>72386991504</td>
      <td>41340080</td>
      <td>Caminho 20-Setor 02</td>
      <td>Cajazeiras</td>
      <td>Salvador</td>
      <td>BA</td>
      <td>338595</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>5</td>
      <td>488</td>
      <td>2440</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Guilherme Yago Manoel Teixeira</td>
      <td>31373115190</td>
      <td>40290635</td>
      <td>2ª Travessa da China</td>
      <td>Acupe de Brotas</td>
      <td>Salvador</td>
      <td>BA</td>
      <td>248303</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>2</td>
      <td>725</td>
      <td>1450</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Lavínia Clarice Luciana Silva</td>
      <td>54617353127</td>
      <td>73813530</td>
      <td>Travessa 13</td>
      <td>Formosinha</td>
      <td>Formosa</td>
      <td>GO</td>
      <td>253537</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>4</td>
      <td>794</td>
      <td>3176</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Pietro Davi Silveira</td>
      <td>81065601808</td>
      <td>57061660</td>
      <td>Rua João Batista</td>
      <td>Tabuleiro do Martins</td>
      <td>Maceió</td>
      <td>AL</td>
      <td>153307</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>7</td>
      <td>420</td>
      <td>2940</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Thiago Tiago Renato Almeida</td>
      <td>19491985108</td>
      <td>78155160</td>
      <td>Rua Paulo Afonso</td>
      <td>São Marcos</td>
      <td>Várzea Grande</td>
      <td>MT</td>
      <td>213601</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>3</td>
      <td>343</td>
      <td>1029</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Alice Gabrielly Galvão</td>
      <td>35156879470</td>
      <td>68928111</td>
      <td>Travessa I</td>
      <td>Paraíso</td>
      <td>Santana</td>
      <td>AP</td>
      <td>534596</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>2</td>
      <td>976</td>
      <td>1952</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Mateus Vitor da Silva</td>
      <td>11373151641</td>
      <td>41290380</td>
      <td>Travessa Santo Antônio</td>
      <td>Pirajá</td>
      <td>Salvador</td>
      <td>BA</td>
      <td>623260</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>5</td>
      <td>633</td>
      <td>3165</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Luana Pietra Luciana Peixoto</td>
      <td>79087727810</td>
      <td>52051140</td>
      <td>Rua Treinador Cláudio Coutinho</td>
      <td>Tamarineira</td>
      <td>Recife</td>
      <td>PE</td>
      <td>637467</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>10</td>
      <td>141</td>
      <td>1410</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Diogo Luan Novaes</td>
      <td>26602467182</td>
      <td>33822508</td>
      <td>Rua Existente</td>
      <td>Vereda</td>
      <td>Ribeirão das Neves</td>
      <td>MG</td>
      <td>644472</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>4</td>
      <td>778</td>
      <td>3112</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Emanuel Arthur Guilherme Almada</td>
      <td>42907367188</td>
      <td>81170646</td>
      <td>Rua Osmar Lipinski</td>
      <td>Cidade Industrial</td>
      <td>Curitiba</td>
      <td>PR</td>
      <td>937283</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>2</td>
      <td>784</td>
      <td>1568</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Murilo César Nascimento</td>
      <td>71419355414</td>
      <td>59104267</td>
      <td>4ª Travessa Santo Inácio de Loyola</td>
      <td>Igapó</td>
      <td>Natal</td>
      <td>RN</td>
      <td>480621</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>10</td>
      <td>436</td>
      <td>4360</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Jennifer Vanessa Amanda dos Santos</td>
      <td>49037173802</td>
      <td>35900776</td>
      <td>Rua B</td>
      <td>Vila Salica</td>
      <td>Itabira</td>
      <td>MG</td>
      <td>755781</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>6</td>
      <td>679</td>
      <td>4074</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Márcio Diogo Cauã Freitas</td>
      <td>72002560641</td>
      <td>56316635</td>
      <td>Avenida Frei Damião</td>
      <td>João de Deus</td>
      <td>Petrolina</td>
      <td>PE</td>
      <td>653384</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>1</td>
      <td>405</td>
      <td>405</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Kauê Carlos Duarte</td>
      <td>32488154695</td>
      <td>4015012</td>
      <td>Rua Joaquim Távora</td>
      <td>Vila Mariana</td>
      <td>São Paulo</td>
      <td>SP</td>
      <td>578486</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>5</td>
      <td>134</td>
      <td>670</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Mateus Manoel Vieira</td>
      <td>87420032610</td>
      <td>67146037</td>
      <td>Quadra Trinta e Sete</td>
      <td>Maguari</td>
      <td>Ananindeua</td>
      <td>PA</td>
      <td>849023</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>8</td>
      <td>854</td>
      <td>6832</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Lúcia Lara Sueli Barros</td>
      <td>67866395853</td>
      <td>69902738</td>
      <td>Rua Nobre</td>
      <td>Chico Mendes</td>
      <td>Rio Branco</td>
      <td>AC</td>
      <td>214145</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>9</td>
      <td>212</td>
      <td>1908</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Isabella Heloise Moraes</td>
      <td>51545705372</td>
      <td>60767370</td>
      <td>Rua F</td>
      <td>Mondubim</td>
      <td>Fortaleza</td>
      <td>CE</td>
      <td>290348</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>6</td>
      <td>470</td>
      <td>2820</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Manuela Hadassa Nair de Paula</td>
      <td>78550813729</td>
      <td>72270418</td>
      <td>Quadra QNQ 4 Conjunto 18</td>
      <td>Ceilândia Norte (Ceilândia)</td>
      <td>Brasília</td>
      <td>DF</td>
      <td>191108</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>9</td>
      <td>912</td>
      <td>8208</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Gustavo Diego Gabriel da Conceição</td>
      <td>92100026100</td>
      <td>72320569</td>
      <td>Quadra QN 414 Conjunto I</td>
      <td>Samambaia Norte (Samambaia)</td>
      <td>Brasília</td>
      <td>DF</td>
      <td>193798</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>2</td>
      <td>557</td>
      <td>1114</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Sarah Alícia Fernandes</td>
      <td>59408458435</td>
      <td>78015245</td>
      <td>Rua João Barbosa Farias</td>
      <td>Dom Aquino</td>
      <td>Cuiabá</td>
      <td>MT</td>
      <td>796878</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>4</td>
      <td>951</td>
      <td>3804</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Heitor Marcos Lucca das Neves</td>
      <td>54121182677</td>
      <td>72502607</td>
      <td>Quadra QR 402 Conjunto G</td>
      <td>Santa Maria</td>
      <td>Brasília</td>
      <td>DF</td>
      <td>723821</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>7</td>
      <td>564</td>
      <td>3948</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Eduarda Malu Luciana Figueiredo</td>
      <td>10266544088</td>
      <td>37705032</td>
      <td>Rua Newton Romanelli</td>
      <td>Jardim das Hortênsias</td>
      <td>Poços de Caldas</td>
      <td>MG</td>
      <td>312345</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>7</td>
      <td>937</td>
      <td>6559</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Thiago Theo Alexandre Brito</td>
      <td>45146212775</td>
      <td>69151240</td>
      <td>Rua Marechal Castelo Branco</td>
      <td>Centro</td>
      <td>Parintins</td>
      <td>AM</td>
      <td>994124</td>
      <td>Nota referente aos serviços prestados/produtos...</td>
      <td>1</td>
      <td>617</td>
      <td>617</td>
    </tr>
  </tbody>
</table>
</div>



```python
#Rodar preenchimento para cada cliente
for linha in tabela.index:
    # Preencher formulario
    #Razao social
    navegador.find_element(By.NAME,'nome').send_keys(tabela.loc[linha,'Cliente'])
    #Endereco
    navegador.find_element(By.NAME,'endereco').send_keys(tabela.loc[linha,'Endereço'])
    #Bairro
    navegador.find_element(By.NAME,'bairro').send_keys(tabela.loc[linha,'Bairro'])
    #Municipio
    navegador.find_element(By.NAME,'municipio').send_keys(tabela.loc[linha,'Municipio'])
    #CEP
    navegador.find_element(By.NAME,'cep').send_keys(str(tabela.loc[linha,'CEP']))
    #UF
    navegador.find_element(By.NAME,'uf').send_keys(tabela.loc[linha,'UF'])
    #CNPJ
    navegador.find_element(By.NAME,'cnpj').send_keys(str(tabela.loc[linha,'CPF/CNPJ']))
    #Inscricao
    navegador.find_element(By.NAME,'inscricao').send_keys(str(tabela.loc[linha,'Inscricao Estadual']))
    #Descricao
    navegador.find_element(By.NAME,'descricao').send_keys(tabela.loc[linha,'Descrição'])
    #Quantidade
    navegador.find_element(By.NAME,'quantidade').send_keys(str(tabela.loc[linha,'Quantidade']))
    #Vlr unt
    navegador.find_element(By.NAME,'valor_unitario').send_keys(str(tabela.loc[linha,'Valor Unitario']))
    #Vlr Total
    navegador.find_element(By.NAME,'total').send_keys(str(tabela.loc[linha,'Valor Total']))
    #Clicar botão Emitir nota
    navegador.find_element(By.CLASS_NAME,'registerbtn').click()
    navegador.refresh()
    
```


    ---------------------------------------------------------------------------

    KeyboardInterrupt                         Traceback (most recent call last)

    <ipython-input-46-bb84e6480270> in <module>
          7     navegador.find_element(By.NAME,'endereco').send_keys(tabela.loc[linha,'Endereço'])
          8     #Bairro
    ----> 9     navegador.find_element(By.NAME,'bairro').send_keys(tabela.loc[linha,'Bairro'])
         10     #Municipio
         11     navegador.find_element(By.NAME,'municipio').send_keys(tabela.loc[linha,'Municipio'])
    

    ~\anaconda3\lib\site-packages\selenium\webdriver\remote\webelement.py in send_keys(self, *value)
        538                 value = '\n'.join(remote_files)
        539 
    --> 540         self._execute(Command.SEND_KEYS_TO_ELEMENT,
        541                       {'text': "".join(keys_to_typing(value)),
        542                        'value': keys_to_typing(value)})
    

    ~\anaconda3\lib\site-packages\selenium\webdriver\remote\webelement.py in _execute(self, command, params)
        708             params = {}
        709         params['id'] = self._id
    --> 710         return self._parent.execute(command, params)
        711 
        712     def find_element(self, by=By.ID, value=None):
    

    ~\anaconda3\lib\site-packages\selenium\webdriver\remote\webdriver.py in execute(self, driver_command, params)
        421 
        422         params = self._wrap_value(params)
    --> 423         response = self.command_executor.execute(driver_command, params)
        424         if response:
        425             self.error_handler.check_response(response)
    

    ~\anaconda3\lib\site-packages\selenium\webdriver\remote\remote_connection.py in execute(self, command, params)
        331         data = utils.dump_json(params)
        332         url = f"{self._url}{path}"
    --> 333         return self._request(command_info[0], url, body=data)
        334 
        335     def _request(self, method, url, body=None):
    

    ~\anaconda3\lib\site-packages\selenium\webdriver\remote\remote_connection.py in _request(self, method, url, body)
        353 
        354         if self.keep_alive:
    --> 355             resp = self._conn.request(method, url, body=body, headers=headers)
        356             statuscode = resp.status
        357         else:
    

    ~\anaconda3\lib\site-packages\urllib3\request.py in request(self, method, url, fields, headers, **urlopen_kw)
         76             )
         77         else:
    ---> 78             return self.request_encode_body(
         79                 method, url, fields=fields, headers=headers, **urlopen_kw
         80             )
    

    ~\anaconda3\lib\site-packages\urllib3\request.py in request_encode_body(self, method, url, fields, headers, encode_multipart, multipart_boundary, **urlopen_kw)
        168         extra_kw.update(urlopen_kw)
        169 
    --> 170         return self.urlopen(method, url, **extra_kw)
    

    ~\anaconda3\lib\site-packages\urllib3\poolmanager.py in urlopen(self, method, url, redirect, **kw)
        373             response = conn.urlopen(method, url, **kw)
        374         else:
    --> 375             response = conn.urlopen(method, u.request_uri, **kw)
        376 
        377         redirect_location = redirect and response.get_redirect_location()
    

    ~\anaconda3\lib\site-packages\urllib3\connectionpool.py in urlopen(self, method, url, body, headers, retries, redirect, assert_same_host, timeout, pool_timeout, release_conn, chunked, body_pos, **response_kw)
        697 
        698             # Make the request on the httplib connection object.
    --> 699             httplib_response = self._make_request(
        700                 conn,
        701                 method,
    

    ~\anaconda3\lib\site-packages\urllib3\connectionpool.py in _make_request(self, conn, method, url, timeout, chunked, **httplib_request_kw)
        443                     # Python 3 (including for exceptions like SystemExit).
        444                     # Otherwise it looks like a bug in the code.
    --> 445                     six.raise_from(e, None)
        446         except (SocketTimeout, BaseSSLError, SocketError) as e:
        447             self._raise_timeout(err=e, url=url, timeout_value=read_timeout)
    

    ~\anaconda3\lib\site-packages\urllib3\packages\six.py in raise_from(value, from_value)
    

    ~\anaconda3\lib\site-packages\urllib3\connectionpool.py in _make_request(self, conn, method, url, timeout, chunked, **httplib_request_kw)
        438                 # Python 3
        439                 try:
    --> 440                     httplib_response = conn.getresponse()
        441                 except BaseException as e:
        442                     # Remove the TypeError from the exception chain in
    

    ~\anaconda3\lib\http\client.py in getresponse(self)
       1345         try:
       1346             try:
    -> 1347                 response.begin()
       1348             except ConnectionError:
       1349                 self.close()
    

    ~\anaconda3\lib\http\client.py in begin(self)
        305         # read until we get a non-100 response
        306         while True:
    --> 307             version, status, reason = self._read_status()
        308             if status != CONTINUE:
        309                 break
    

    ~\anaconda3\lib\http\client.py in _read_status(self)
        266 
        267     def _read_status(self):
    --> 268         line = str(self.fp.readline(_MAXLINE + 1), "iso-8859-1")
        269         if len(line) > _MAXLINE:
        270             raise LineTooLong("status line")
    

    ~\anaconda3\lib\socket.py in readinto(self, b)
        667         while True:
        668             try:
    --> 669                 return self._sock.recv_into(b)
        670             except timeout:
        671                 self._timeout_occurred = True
    

    KeyboardInterrupt: 



```python
navegador.quit()
```


```python

```
