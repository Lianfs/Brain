<template>
    <div class="container">
        <div class="materia">
            <h6 class="texto-materias">Todas</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Matemática</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">História</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Geografia</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Biologia</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Português</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Física</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Química</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Filosofia</h6>
        </div>
        <div class="materia">
            <h6 class="texto-materias">Sociologia</h6>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style scoped>
.container{
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 30px;
    height: 120px;
    border-bottom: 1.5px solid rgba(128, 128, 128, 0.281);
}

.materia{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 90px;
    height: 60px;
    margin: 20px;
}

.quadrado-materia{
    width: 20px;
    height: 20px;
    border: 1px solid gray;
}

.materia:hover > .texto-materias{
    transform: translateY(-5px);
}

.texto-materias{
    font-size: 12px;
    line-height: 16px;
    font-weight: 700;
    color: #687b8c;
    bottom: 0;
    transition: 0.2s;
}
</style>