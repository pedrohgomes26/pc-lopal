# pc-lopal
Repositório para armazenar os códigos da aula


# Desafio 1
## Significado dos tres numeros da versão
Os tres numeros são conhecidos como **Versionamento Semântico** em inglês **Semantic Versioning**, ele e um padrão universal escolhido pela comunidade de desenvolvimento para explicar o risco e o impacto de atualizar um codigo

## O que cada numero representa
#### Major
O primeiro numero e o **Major** ele e a **versão maior** que significa mudanças drásticas, quando esse numero aumenta quer dizer que teve alterações incompativeis com as versões anteriores um exemplo de atualização  do major e da 1.5.8 para 2.0.0
### Minor
O segundo numero representa o **Minor** ele e a **versão menor**, ele apresenta  novas funcionalidades que significa que recursos novos foram adicionados sendo compatíveis com o codigo que ja existia um bom exemplo para o minor e o jogo minecraft que sempre vai atualizando na versão minor, um exemplo e a atualização 1.18.0 que trouxe novas funções para o jogo.
### Patch
O terceiro numero representa o **Patch** que e a **correção** de algum bug, normalmente o patch e o que mais sofre atualizações pois quase sempre tem alguns bugs que não foram vistos, basicamente o patch não adiciona nada ele apenas corrige os erros e bugs que o codigo podia ter

### Quem decide as mudanças
Quem decide são os propios desenvolvedores criadores do codigo, e eles tomam essa decisão se baseando especificamente nas modificações que foram feitas  em relação a versão anterior

# Desafio 2
## Diferença entre os dois grupos
A diferença do dependencies para o devDependencies e que o dependencies são as bibliotecas importantes elas são necessaria para que a aplicação funcione quando estiver rodando no ar enquanto a devDependencies são as bibliotecas usadas como ferramenta  durante a fase de desenvolvimento como testes e validações elas so são necessarias na hora de ajudar o desenvolvedor na criação do codigo, não precisam estar no servidor de produção final
## Qual grupo colocar uma biblioteca
Na devDependencies escolha apenas as bibliotecas que forem te ajudar a desenvolver e criar o codigo um exemplo e a biblioteca Prettier que e um formatador de código automatico que reorganiza e padroniza visualmente o seu código. Na dependencies você escolhe aquelas que são necessarias para o codigo conseguir funcionar

# Desafio 3
## O que cada símbolo permite atualizar?
### Circunflexo (^)
O **(^) ->** **Circunflexo** e o que garante que não ocorra uma atualização **Major** ele apenas permite que o gerenciador de pacotes atualize o **Minor** e o **Patch** por exemplo se você tem a versão **^1.2.3** o gerenciador so vai baixar ate o **Minor** e o **Patch** mais recente.

### Til (~)
O **(~) ->** **Til** trava o seu **Major** e **Minor** permitindo que apenas o **Patch** seja atualizado, liberando atualizações apenas para correções de bugs. Por exemplo se você tem a versão **~1.2.3** você vai poder atualizar ela para a **1.2.4** **1.2.9** e assim por diante
## Quando não tem um símbolo
Se não estiver com  símbolo nenhum ele vai travar nessa versão e você não vai conseguir atualizar o **Major** o **Minor** ou o **Patch** de forma automatica, para alterar você tera que trocar manualmente o numero da versão você mesmo.

# Desafio 4
## O que cada símbolo permite atualizar?
### Circunflexo (^)
O **(^) ->** **Circunflexo** e o que garante que não ocorra uma atualização **Major** ele apenas permite que o gerenciador de pacotes atualize o **Minor** e o **Patch** por exemplo se você tem a versão **^1.2.3** o gerenciador so vai baixar ate o **Minor** e o **Patch** mais recente.

### Til (~)
## Diferença entre os dois
O **commonJS** e **dinamico** então o código so e lido na hora em que o programa está rodando. E por isso você via precisar botar um **require()** dentro de um if, de um for ou de uma função. Ja o **ES Modules** que e **estático** usa o **import** que utiliza motor do JavaScript para ler todos os **imports** antes de executar alguma linha de codigo. Por ser estatico os **imports** so precisa ficar obrigatoriamente no topo do arquivo pra funcionar

## Como surgiu
### CommonJS (CJS)
O **CommonJS** surgiu aproximadamente em **2009** e originalmente era chamado de **ServerJS**, o projeto nasceu da necessidade da comunidade de usar JavaScript fora dos navegadores, então o **node.js** adotou o **CommonJS** como seu sistema padrão de modulos logo no início. Então por anos, o **CommonJS** foi o padrão de fato para desenvolvimento backend em JavaScript
### ES Module (ESM)
Foi criado em 2015 (com a especificaçãoECMAScript 2015) como o **JavaScript** não tinha um sistema de módulos oficial na própia linguagem. Então o **TC39 (comitê do JS)** criou o **ES Modules** para ser o padrão oficial e nativo, projetado para funcionar tanto no navegador quanto no servidor

## Sintaxes de cada um
### Exportando no CommonJS
    function somar(a, b) {
        return a + b};
    const PI = 3.14159

    module.exports = { 
        somar,
        PI
    };
    
    class Usuario {
        contructor(nome) {
            this.nome = nome;
        }
    }
    
    module.exports = Usuario;
### Importando no CommonJS
    const { somar, PI } = require('./exportação-name')
    const Usuario = require('./exportação-default')

    console.log(somar(2, 3)) // resultado 5
    const user = new Usuario('Ana')

### Exportando em ES Module
    export function somar(a, b) {
        return a + b;
    }

    export const PI = 3.14159;

    export default class Usuario {
        constructor(nome) {
            this.nome = nome;
        }
    }
### Importando em ES Module
    import Usuario from 'exportação-default.js';
    import {somar, PI} from 'exportação-name.js';

    import * as MathUtils from './exportacao-name.js';

    console.log(somar(2, 3)) // resultado 5
    console.log(MathUtils.PI) // 3.14159