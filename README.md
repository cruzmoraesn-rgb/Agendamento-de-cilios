<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Agendamento de Cílios</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #fdecef;
            margin: 0;
            padding: 0;
        }
        header {
            background: #e91e63;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .container {
            max-width: 500px;
            background: white;
            margin: 30px auto;
            padding: 20px;
            border-radius: 10px;
        }
        h2 {
            text-align: center;
            color: #e91e63;
        }
        label {
            display: block;
            margin-top: 15px;
        }
        input, select {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        button {
            margin-top: 20px;
            width: 100%;
            padding: 12px;
            background: #e91e63;
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            cursor: pointer;
        }
        button:hover {
            background: #d81b60;
        }
        footer {
            text-align: center;
            padding: 10px;
            color: #777;
            font-size: 14px;
        }
    </style>
</head>
<body>

<header>
    <h1>Studio de Cílios</h1>
    <p>Agende seu horário online 💖</p>
</header>

<div class="container">
    <h2>Agendamento</h2>
    <form onsubmit="enviarAgendamento(event)">
        <label>Nome:</label>
        <input type="text" id="nome" required>

        <label>Telefone:</label>
        <input type="tel" id="telefone" required>

        <label>Serviço:</label>
        <select id="servico" required>
            <option value="">Selecione</option>
            <option>Cílios Clássico</option>
            <option>Volume Brasileiro</option>
            <option>Volume Russo</option>
            <option>Manutenção</option>
        </select>

        <label>Data:</label>
        <input type="date" id="data" required>

        <label>Horário:</label>
        <input type="time" id="hora" required>

        <button type="submit">Agendar</button>
    </form>
</div>

<footer>
    © 2025 Studio de Cílios
</footer>

<script>
    function enviarAgendamento(event) {
        event.preventDefault();

        const nome = document.getElementById("nome").value;
        const telefone = document.getElementById("telefone").value;
        const servico = document.getElementById("servico").value;
        const data = document.getElementById("data").value;
        const hora = document.getElementById("hora").value;

        const mensagem =
            `✨ NOVO AGENDAMENTO ✨\n\n` +
            `Nome: ${nome}\n` +
            `Telefone: ${telefone}\n` +
            `Serviço: ${servico}\n` +
            `Data: ${data}\n` +
            `Horário: ${hora}`;

        const telefoneStudio = "5543984772247";

        const url = 
          `https://api.whatsapp.com/send?phone=${telefoneStudio}&text=${encodeURIComponent(mensagem)}`;

        window.open(url, "_blank");
    }
</script>

</body>
</html>
