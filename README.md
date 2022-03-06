# -Registrando-um-bloco-Jscript-
Registrando um bloco Jscript dinamicamente usando o método RegisterOnSubmitStatement da classe Page.

<%@ Page Language="#" %>

public void Page_Load(object sender , EventArgs e) {

// Montando o código script que será registrado no cliente,
StringBuilder bloco = new ScringBulder();
bloco.Append("<Script language= Javascript > fuction CliqueBotao() {");
bloco.Append("window.a lert(fom.show.valeu + , só , Net salva tua vida! ); }");
bloco.Append("</");
bloco.Append("Script>");
//Poderia tre juntado tudo numa linha só mas, caso
//eu tivesse feito isso o webmatrix ia confundir essa
//palavra script com a palavra script do bloco runat=server

//a função IsClientScriptBlockRegistered verifica se o bloco já foi registrado
if(!Paga.IsClientScriptBlockRegistered("script"))
    //O primerio parámetro da função é um indentificador para o bloco script.
    Paga. RegisterclientscriptBlock("scripteste", bloco.ToString());

    //Registrando a função script que deve ser chamado no evento Onsubmit.
    //Um exemplo legal seria colocar uma função que fizesse alguma validação e caso,
    //comtrário, interrompesse o submit.
    Paga. RegisterronSubmitStatement("scriptonSubmit" , "CliqueBotao()");
}
</script>
<html>
<head>
</head>
<body tomargin="20">
    <form id="runat="server">
        Digite seu nome;
        <input id="srtyle="WIDTH: 200px" type="text" />
        <asp:Button id="btncliqueok" runat="server" Text="clique ok"></asp:Button>
    </from>
</body>
</html>   
 
