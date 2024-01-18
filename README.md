# Projeto Relógio Digital

Este simples projeto em JavaScript exibe um relógio com a hora atual, incluindo horas, minutos, segundos e AM/PM. Além disso, ele mostra uma mensagem de boas-vindas juntamente com a data atual no formato "dd/MM/yyyy".

## Estrutura do Projeto

O projeto consiste em um único arquivo HTML e um script JavaScript:

### Arquivos:

- **index.html**: O arquivo HTML que contém a estrutura da página web.
  
- **script.js**: O arquivo JavaScript que contém a lógica para atualizar o relógio e exibir a data.

## Exibição do Relógio

A exibição do relógio é dividida em quatro elementos:

- **hour**: Exibe a hora atual.
  
- **minutes**: Exibe os minutos atuais.
  
- **seconds**: Exibe os segundos atuais.
  
- **ampm**: Exibe "AM" ou "PM" dependendo do horário atual.

## Exibição da Data

A mensagem de boas-vindas inclui a cidade "Londrina" e a data atual no formato "dd/MM/yyyy". A data é atualizada juntamente com o horário.

Abaixo o resultado do projeto exibido no navegador.

<a href="https://ibb.co/6WsFmpd"><img src="https://i.ibb.co/wz64Rbv/resultado-projeto-relogio-digital.png" alt="resultado-projeto-relogio-digital" border="0"></a>

## Funcionalidade

A função JavaScript `updateClock()` obtém a hora e a data atuais usando o objeto `Date`. Ela formata a hora, atualiza os elementos HTML e define um timeout para atualizar o relógio a cada segundo.

```javascript
const hourEl = document.getElementById("hour");
const minuteEl = document.getElementById('minutes');
const secondEl = document.getElementById("seconds");
const ampmEl = document.getElementById("ampm");
const welcomeEl = document.getElementById("welcome");

function updateClock(){
    let h = new Date().getHours();
    let m = new Date().getMinutes();
    let s = new Date().getSeconds();
    let ampm = "AM";
    let welcomeTime = new Date();

    let formattedDate = welcomeTime.toLocaleDateString("pt-BR", {day: '2-digit', month:'2-digit', year:'numeric'});
    
    if (h > 12) {
        h = h - 12;
        ampm = "PM";
    }

    h = h < 10 ? "0" + h : h;
    m = m < 10 ? "0" + m : m;
    s = s < 10 ? "0" + s : s;
   
     hourEl.innerText = h;
     minuteEl.innerText = m;
     secondEl.innerText = s;
     ampmEl.innerText = ampm;
     welcomeEl.innerHTML = "Londrina, " + formattedDate;

     setTimeout(()=>{
        updateClock()
     }, 1000);
}

updateClock();
```

## Executando o Projeto

Basta abrir o arquivo `index.html` em um navegador da web para visualizar o projeto do relógio em ação.

Sinta-se à vontade para modificar ou aprimorar o projeto conforme necessário!

### Paulo Santos