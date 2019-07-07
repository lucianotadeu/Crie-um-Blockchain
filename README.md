# Crie um Blockchain
Avaliação da disciplina Blockchain Platform no curso MBA Blockchain - FIAP
 
## Descrição
Construa um blockchain em planilha google ou excel
 
### Alternativas para o trabalho
Pode-se entregar o trabalho criando a mesma base com alguma linguagem como Python, javascript, c#, etc
Se apresentar publicado com uma interface gráfica, como a do anders, tem ponto extra!
 
 
## Requisitos (itens da avaliação)
Blocos
 
Transações
 
Hash SHA256
 
PoW e Nonce- "botão" para mineração
 
Dificuldade da rede 1000 (ou seja, blocos começando com 000)
 
Fee
 
Troco
 
 
Possibilidade de alterar as transações e ver as consequências
 
Pelo menos 5 blocos
 
Deve ter taxa de minerador
 
Deve mostrar o que acontece se não for definido para onde vai o troco.
 
 
## Entrega
 
Faça um clone deste repositório (não faça fork)
 
### Data final
7/julho/2019 às 23h59 (GMT-3)
 



### O que entregar
Link para o repositório no github

https://github.com/lucianotadeu/fiap-blc-blockchainplatform.git

### O que deve conter no repositório
nomes dos integrantes do grupo
RM 334333 - ADONAI MARTINHO MOREIRA
RM 334164 - LUCIANO TADEU PEREIRA
RM 335054 - RODRIGO DE ARRUDA MENDES
RM 333458 - SÉRGIO LUÍS CAMPOS DOS SANTO

processo de desenvolvimento do trabalho
explicação sobre seu Blockchain
Pesquisa referente a como desenvolver a dinâmica do Blockchain em planilha do Google através da pesquisa descobrimos o vídeo explicativo do site tribocrypto.com / https://www.youtube.com/watch?v=NZHk-mxs45w com base na explicação acrescentamos 
a function TesteLup(param, difficulty, nonce) que segue abaixo para a mineração do nonce.


function TesteLup(param, difficulty, nonce){
  
  var target = TesteB(param, difficulty, nonce); 
  
  while(target == "Bloco Inválido"){
    nonce += 1;
    
    target = TesteB(param, difficulty, nonce);
  
  }
  
  return nonce;
  
}

function TesteB(param, difficulty, nonce){
  var concat = param + ", " + difficulty + ", " + nonce;
  var hash = GetSHA256Hash(concat);
  var target = CheckTarget(difficulty, hash);
  
  return target;
}


function Nonce() {
  var spreadsheet = SpreadsheetApp.getActive();
  spreadsheet.getRange('C9').activate();
  spreadsheet.getCurrentCell().setValue('1');
  spreadsheet.getRange('C10').copyTo(spreadsheet.getActiveRange(), SpreadsheetApp.CopyPasteType.PASTE_VALUES, false);
};


referências utilizadas
tribocrypto.com
 

https://www.youtube.com/watch?v=NZHk-mxs45w
 
se for "google sheet": link para a planilha

https://docs.google.com/spreadsheets/d/1vLNxy4r8sSHoiH-Q_ha2bPUAiVcTtQytPFMJnPo5TJE/edit?usp=sharing


Incluir também na planilha:
A primeira aba deve conter os nomes dos integrantes do grupo e explicação sobre seu Blockchain
 
## Referências
item Coinbase do Blockchain Anders
https://anders.com/blockchain/coinbase.html
 
