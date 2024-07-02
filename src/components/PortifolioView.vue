<template>

    <div>
            <!---Header-->
    <header>

        <nav class="navbar nav-light bg-primary">

            <!---IMAGES-->
            <div class="container mt-3">

                <div class="row">

                    <div class="col d-flex justify-content-center">
                        <img class="img-fluid w-50 img1" src="../assets/img/js.jpg" alt="">
                    </div>

                    <div class="col d-flex justify-content-center">
                        <img class="img-fluid w-50 img2" src="../assets/img/node.png" alt="">
                    </div>

                    <div class="col d-flex justify-content-center">
                        <img class="img-fluid w-50 img3" src="../assets/img/vue.png" alt="">
                    </div>

                </div>
            </div>
            
            
        </nav>
        
    </header> <!---Fim Header-->


    <!---Principal-->
    <main>

        <div class="container-fluid bg-dark">

            <div class="row">

                <div class="col-12 text-center">

                    <img class="img-fluid photo mt-5" src="../assets/img/foto_perfil_2.jpg" alt="foto de perfil">

                    <h1 class="text-light mt-4" style="font-family: 'Times New Roman', Times, serif;">Victor Zaidir</h1>

                    <p class="text-light lead">{{msg}}</p>
                    <p class="text-light lead">Saltinho, Sao Paulo, Brasil</p>
                    <p class="text-light lead">Estudando desenvolvimento web cerca De 10 meses</p>


                    <a href="https://github.com/Zdvictor/Projeto-Portfolio/blob/main/pdf/Currículo.pdf" class="btn btn-success btn-lg m-2">BAIXAR CV</a>
                    <a href="https://www.linkedin.com/in/victor-%E3%85%A4-04a695303/" class="btn btn-primary btn-lg">VER LINKEDIN</a>     


                    <div class="mt-5 mb-5">
                        <img class="img-fluid" style="width: 22px; height: 24px;" src="../assets/icons/whatsapp.svg" alt="Icone Para Contato Whats">            
                        <p class="text-success">Envie Uma Mensagem Para:</p>
                        <a href="https://api.whatsapp.com/send?phone=5515991105703&text=Olá,%20Tudo%20bem" class="btn btn-success text-light">Whatsapp: (15) 99110-5703</a>
                        <br><br><br><br>
                        
                    </div>
                    
                                        

                    
                </div>


            </div>


        </div>


    </main> <!---Fim Principal-->


            <!---Inicio Section-->
    <section>

        <div class="bg-info">

            <div class="container pt-5">

                <div class="row">
                    <div class="col-12 text-center mt-4">

                        <h2 class="text-light">PROJETOS 🔥🔥</h2>

                        <hr>

                            <div class="row mt-5 logos pb-5">

                                <div class="col-4 hidden " :class="{show: ativado}" >

                                    <button @click="openModal(1)" class="btn btn-success btn-lg" href="">

                                        <img width="200px" height="150px" class="img-fluid img1" src="../assets/img/projects/futschool.png" alt="">
            
                                    </button>

                                </div>

                                <div class="col-4 hidden" :class="{show: ativado}" >

                                    <button @click="openModal(2)" class="btn btn-success btn-lg" href="">

                                        <img width="500px" height="150px" class="img-fluid img2" src="../assets/img/projects/plaze.png" alt="">
            
                                    </button>
                                    
                                </div>

                                <div class="col-4 hidden" :class="{show: ativado}">

                                    <button @click="openModal(3)" class="btn btn-success btn-lg" href="">

                                        <img width="200px" height="150px" class="img-fluid img3" src="../assets/img/projects/mines.png" alt="">
            
                                    </button>
                                    
                                </div>


                            </div>


                            <hr>


                    </div>
                </div>

            </div>


        </div>

    
    
    </section><!---Fim Section-->


    <!---Modal--->
    <Modal :title="title" :desc="desc" :src="src" />

  


    <footer>

        <!----Nada Por Enquanto-->


    </footer>

    </div>


  
</template>

<script>

import Modal from '../components/partials/ModalView.vue'

export default {

    components: {

      Modal

    },
    
    data() {

        return {

            ativado: false,
            msg: '',
            title: '',
            desc: '',
            src: ''


        }


    },

created() {

  var message = 'DESENVOLVEDOR FULL STACK | JAVASCRIPT, TYPESCRIPT, VUE.JS , NODE.JS';
  var tempo = 125

  var caracter = 0
  
  let iniciarFunction = () => {

    if(caracter < message.length) {

        this.msg += message[caracter]
        caracter++

        setTimeout(iniciarFunction,tempo)

    }


  }

  iniciarFunction()


},


  mounted() {
    
    let myObserver = new IntersectionObserver( (entries) => {


    entries.forEach( (entry) => {


        if(entry.isIntersecting) {
            
            
            this.ativado = true


        }else {

            
            this.ativado = false


        }


    })


})


let elements = document.querySelectorAll('.hidden')


elements.forEach( element => {


    myObserver.observe(element)


})

  },


  methods: {

    openModal(value) {

      if(value == 1){

        this.title = 'Projeto FutSchool'
        this.desc = 'Este projeto foi desenvolvido em 2023, enquanto eu estudava desenvolvimento web (HTML, CSS, Bootstrap).Ele consiste em uma escola de futebol fictícia.';
        this.src = 'https://zdvictor.github.io/projeto-FutSchool/'


      }

      if(value == 2){

        this.title = 'Plaze'
        this.desc = 'Este projeto foi desenvolvido no final de 2023, enquanto eu estudava desenvolvimento web (HTML, CSS, Bootstrap e JavaScript). Ele consiste em uma casa de apostas fictícia.'
        this.src = 'https://zdvictor.github.io/projeto-Plaze/'


      }

      if(value == 3){

        this.title = 'Projeto Mines'
        this.desc = 'Este projeto (jogo) foi desenvolvido em 2024, após eu finalizar o curso completo de desenvolvimento web front-end. Coloquei em prática o jogo com lógica de programação em JavaScript.'
        this.src = 'https://zdvictor.github.io/projeto-Mines/'


      }
      
      document.querySelector('#btnopen').click()


    }


  }


};


</script>

<style>

@keyframes startApplication {
  0% {
    
    opacity: 0.5;
  }
  100% {
    opacity: 1;
  }
}

@keyframes slideLeft1 {
    0% {
      transform: translateX(-700%);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }

  @keyframes slideLeft2 {
    0% {
      transform: translateX(-5000%);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }

  @keyframes slideLeft3 {
    0% {
      transform: translateX(-7000%);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }
  
  /* Aplica a animação às imagens dentro do header */
    header .img1 {
    animation: slideLeft1 1s backwards;
  }

  header .img2 {
    animation: slideLeft2 2s backwards;
  }

  header .img3 {
    animation: slideLeft3 3s backwards;
  }

  nav{

    animation: startApplication 1s ease;

  }

/* Estilos para as imagens */
.img1 {
    width: 80%; /* 80% de largura original */
}

.img2 {
    width: 70%; /* 70% de largura original */
    
}

.img3 {
    width: 79%; /* 79% de largura original */
    
}


.photo{
    
    width: 200px;
    height: 200px;
    border-radius: 200px;


}

.hidden{

  opacity: 0;
  filter: blur(15px);
  transition: all 2s;
  transform: translateX(-100%);

}

.hiddenn{

  opacity: 0;
  filter: blur(15px);
  transition: all 2s;
  transform: translateX(-100%);

}



.show{

  opacity: 1;
  filter: blur(0);
  transition: all 2s;
  transform: translateX(0);

}

.logos :nth-child(2){

  transition-delay: 400ms;


}

.logos :nth-child(3){

  transition-delay: 700ms;


}

.logos :nth-child(4){

  transition-delay: 1000ms;


}

@media(max-width: 800px) {

  .photo{

    width: 100px;
    height: 100px;
    border-radius: 200px;

  }


}

@media(max-width: 400px) {

  .photo{

    width: 70px;
    height: 70px;
    border-radius: 200px;

  }


}



</style>