<b> Vinícius Oliveira Martinkovitsch </b>
<br /> <br />
<b>Questões</b>
<br /> <br />
<b>1-</b>	Você tem 8 moedas e todas tem o mesmo peso exceto uma, que é um pouco mais pesada que as demais. Você também possui uma balança que permite pesar duas pilhas de moedas para descobrir qual é a mais pesada (ou de mesmo peso). Qual é o mínimo número de combinações para serem feitas para descobrir qual a moeda mais pesada?
<br />
O número mínimo de combinações possíveis são duas combinações, pois, caso a moeda mais pesada esteja no topo da pilha, e ela seja trocada de pilha na pesagem, teremos 2 combinações diferentes.
<br /> <br />
<b>2-</b>	Assuma um cubo semelhante ao do desenho abaixo, no entanto com 8 mini cubos em cada aresta. Se pintarmos todas as suas faces, quantos mini cubos terão pelo menos uma face pintada?
<br />
384 mini cubos terão pelo menos uma face pintada.
<br /> <br />
<b>1-</b> Dado um array de inteiros ordenados, como encontrar a posição de determinado valor?
<br />
<b>Classe em C#, onde foi feito uma interface que retorna os resultados:</b><br />
using System;<br />
using System.Collections.Generic;<br />
using System.ComponentModel;<br />
using System.Data;<br />
using System.Drawing;<br />
using System.Linq;<br />
using System.Text;<br />
using System.Windows.Forms;<br />
<br />
namespace Apontador_Busca<br />
{<br />
    public partial class buscaBinaria : Form<br />
    {<br />
        public buscaBinaria()<br />
        {<br />
            InitializeComponent();<br />
        }<br />
<br />
        static public int BuscaBinaria(int valor)<br />
        {<br />
            int[] numeros = { 2, 3, 5, 7, 9, 11, 13, 14, 16, 17, 19, 20, 22, 23, 24, 25, 27, 29, 30 };<br />
            int min = 0;<br />
            int max = numeros.Length - 1;<br />
            while (max >= min)<br />
            {<br />
                int meio = (min + max) / 2;<br />
<br />
                if (numeros[meio] < valor) min = meio + 1;<br />
<br />
                else if (numeros[meio] > valor) max = meio - 1;<br />
<br />
                else return meio;<br />
            }<br />
<br />
            return -1;<br />
        }<br />
<br />
        private void btnBuscar_Click(object sender, EventArgs e)<br />
        {<br />
            lblNumBuscado.Text = txtNumBusca.Text;<br />
            int numero = Convert.ToInt32(txtNumBusca.Text);<br />
            int resultado = BuscaBinaria(numero);<br />
            if (resultado == -1)<br />
            {<br />
                lblNaoExiste.Visible = true;<br />
                lblPosVet.Text = "";<br />
                lblPosSeq.Text = "";<br />
            }<br />
            else<br />
            {<br />
                lblNaoExiste.Visible = false;<br />
                lblPosVet.Text = Convert.ToString(resultado);<br />
                lblPosSeq.Text = Convert.ToString(resultado + 1);<br />
            }<br />
        }<br />
<br />
    }<br />
}<br />
<br /> <br />
<b>2-</b> Escreva um código para reverter uma string.
<br />
<b>Classe em C#, onde foi feito uma interface que exibe o texto invertido:</b><br />
using System;<br />
using System.Collections.Generic;<br />
using System.ComponentModel;<br />
using System.Data;<br />
using System.Drawing;<br />
using System.Linq;<br />
using System.Text;<br />
using System.Windows.Forms;<br />
<br />
namespace Apontador_InverterTexto<br />
{<br />
    public partial class inverterTexto : Form<br />
    {<br />
        public inverterTexto()<br />
        {<br />
            InitializeComponent();<br />
        }<br />
<br />
        private void inverterTexto_Load(object sender, EventArgs e)<br />
        {<br />
<br />
        }<br />
<br />
        static public string Inverter(string Texto)<br />
        {<br />
            char[] ArrayChar = Texto.ToCharArray();<br />
            Array.Reverse(ArrayChar);<br />
            return new string(ArrayChar);<br />
        }<br />
<br />
        private void btnInverter_Click(object sender, EventArgs e)<br />
        {<br />
            txtTextoResult.Text = Inverter(txtTextoInicial.Text);<br />
        }<br />
    }<br />
}<br />
