<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Reserva</title>
    <link rel="stylesheet" href="formulario.css">
</head>

<body>
    <h1>Formulário de Reserva</h1>
    <form id="reservaForm">
        <label for="ambiente">Ambiente:</label>
        <select id="ambiente" name="ambiente">
            <option value="interno">Interno</option>
            <option value="externo">Externo</option>
        </select><br>

        <label for="nome">Nome:</label>
        <input type="text" id="nome" name="nome" required><br>

        <label for="email">E-mail:</label>
        <input type="email" id="email" name="email" required><br>

        <label for="cardapio">Cardápio:</label>
        <select id="cardapio" name="cardapio">
            <option value="opcao1">Opção 1</option>
            <option value="opcao2">Opção 2</option>
            <option value="opcao3">Opção 3</option>
        </select><br>

        <label for="mesa">Mesa:</label>
        <input type="number" id="mesa" name="mesa" min="1" required><br>

        <button type="submit">Enviar Reserva</button>
    </form>

    <div id="mensagem"></div>

    <script src="formulario.js"></script>
</body>

</html>

body {
    font-family: Arial, sans-serif;
}

form {
    max-width: 400px;
    margin: 0 auto;
}

label {
    display: block;
    margin-bottom: 5px;
}

input[type="text"],
input[type="email"],
select {
    width: 100%;
    margin-bottom: 10px;
    padding: 5px;
}

button {
    padding: 10px 20px;
    background-color: #007bff;
    color: #fff;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

#mensagem {
    margin-top: 20px;
    padding: 10px;
    background-color: #d4edda;
    border: 1px solid #c3e6cb;
    color: #155724;
}


document.getElementById("reservaForm").addEventListener("submit", function(event) {
    event.preventDefault(); // Evita o envio padrão do formulário

    // Coletando os valores do formulário
    var ambiente = document.getElementById("ambiente").value;
    var nome = document.getElementById("nome").value;
    var email = document.getElementById("email").value;
    var cardapio = document.getElementById("cardapio").value;
    var mesa = document.getElementById("mesa").value;

    // Exibindo mensagem de confirmação
    var mensagem = document.getElementById("mensagem");
    mensagem.innerHTML = `<p>Obrigado, ${nome}!</p>
                          <p>Sua reserva para o ambiente ${ambiente}, com o cardápio ${cardapio} e a mesa ${mesa} foi recebida.</p>
                          <p>Um e-mail de confirmação será enviado para ${email}.</p>`;
    // Limpando o formulário
    document.getElementById("reservaForm").reset();
});
