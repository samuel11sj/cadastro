<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Verificação de Usuários</title>
</head>
<body>
  <h1>Cadastro de Usuários</h1>
  <pre id="saida"></pre>

  <script>
    const usuarios = [];
    const anoAtual = new Date().getFullYear();

    for (let i = 1; i <= 3; i++) {
      alert(`Usuário ${i} - Vamos começar!`);

      let nome = prompt("Digite seu nome:");
      let anoNascimento = parseInt(prompt("Digite seu ano de nascimento:"));

      let idade = anoAtual - anoNascimento;

      if (idade >= 18) {
        alert(`Bem-vindo(a), ${nome}! Você tem ${idade} anos.`);

        let nomeUsuario = prompt("Crie um nome de usuário:");
        let senha = prompt("Crie uma senha:");

        usuarios.push({
          nome: nome,
          idade: idade,
          usuario: nomeUsuario,
          senha: senha
        });
      } else {
        alert(`Desculpe, ${nome}. Você tem ${idade} anos e não pode fazer login.`);
      }
    }

    // Convertendo para JSON
    const usuariosJSON = JSON.stringify(usuarios, null, 2);
    console.log(usuariosJSON);
    document.getElementById("saida").textContent = usuariosJSON;
  </script>
</body>
</html>
