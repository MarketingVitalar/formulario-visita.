<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulário de Visita - Agência de Cuidador de Idosos</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f9f9f9;
        }
        form {
            max-width: 600px;
            margin: auto;
            padding: 20px;
            background: #fff;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        label {
            font-weight: bold;
            margin-top: 10px;
            display: block;
        }
        input, select, textarea {
            width: 100%;
            padding: 10px;
            margin: 5px 0 15px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            background-color: #007BFF;
            color: white;
            padding: 10px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #0056b3;
        }
        .hidden {
            display: none;
        }
    </style>
    <script>
        function showSection(value) {
            // Oculta todas as seções
            document.querySelectorAll('.section').forEach(section => {
                section.classList.add('hidden');
            });
            // Mostra a seção correspondente
            const sectionToShow = document.getElementById(value);
            if (sectionToShow) {
                sectionToShow.classList.remove('hidden');
            }
        }
    </script>
</head>
<body>

    <form>
        <h1>Formulário de Visita</h1>
        
        <!-- Pergunta inicial -->
        <label for="tipo_visita">Qual o objetivo da visita?</label>
        <select id="tipo_visita" name="tipo_visita" onchange="showSection(this.value)" required>
            <option value="">Selecione</option>
            <option value="avaliacao_idoso">Avaliação do idoso</option>
            <option value="documentos">Coleta de documentos</option>
            <option value="orientacoes_familia">Orientações para a família</option>
        </select>

        <!-- Seção: Avaliação do idoso -->
        <div id="avaliacao_idoso" class="section hidden">
            <h2>Avaliação do Idoso</h2>
            <label for="nome_idoso">Nome do idoso:</label>
            <input type="text" id="nome_idoso" name="nome_idoso" required>

            <label for="idade_idoso">Idade:</label>
            <input type="number" id="idade_idoso" name="idade_idoso" required>

            <label for="condicao_saude">Condições de saúde:</label>
            <textarea id="condicao_saude" name="condicao_saude" rows="4" required></textarea>
        </div>

        <!-- Seção: Coleta de documentos -->
        <div id="documentos" class="section hidden">
            <h2>Coleta de Documentos</h2>
            <label for="documentos_necessarios">Quais documentos estão disponíveis?</label>
            <textarea id="documentos_necessarios" name="documentos_necessarios" rows="4" required></textarea>

            <label for="responsavel_entrega">Nome do responsável pela entrega:</label>
            <input type="text" id="responsavel_entrega" name="responsavel_entrega" required>
        </div>

        <!-- Seção: Orientações para a família -->
        <div id="orientacoes_familia" class="section hidden">
            <h2>Orientações para a Família</h2>
            <label for="orientacoes">Descreva as orientações fornecidas:</label>
            <textarea id="orientacoes" name="orientacoes" rows="4" required></textarea>

            <label for="dificuldades">Houve alguma dificuldade durante a visita?</label>
            <textarea id="dificuldades" name="dificuldades" rows="4"></textarea>
        </div>

        <button type="submit">Enviar</button>
    </form>

</body>
</html>

