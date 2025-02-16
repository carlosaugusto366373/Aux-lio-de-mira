# Aux-lio-de-mira
using UnityEngine;
using UnityEngine.UI;

public class ControlPanel : MonoBehaviour
{
    // Referências aos elementos da UI
    public GameObject painelControle; // Painel de controle
    public Button btnMinimizar; // Botão para minimizar/expandir o painel
    public Button btnAtivarAuxilio; // Botão para ativar/desativar o auxílio de mira
    public Button btnZoom; // Botão para ativar/desativar o zoom 2x 100%
    public Text textoZoom; // Texto para mostrar o estado do zoom

    private bool auxilioAtivo = false; // Estado do auxílio de mira
    private bool zoomAtivado = false; // Estado do zoom (2x 100%)
    
    void Start()
    {
        // Configurar os listeners dos botões
        btnMinimizar.onClick.AddListener(MinimizarPainel);
        btnAtivarAuxilio.onClick.AddListener(AlternarAuxilio);
        btnZoom.onClick.AddListener(AlternarZoom);

        // Inicializar o estado do painel e dos botões
        painelControle.SetActive(true); // Mostrar painel de controle
        textoZoom.text = "Zoom: Desativado"; // Estado inicial do zoom
    }

    void MinimizarPainel()
    {
        // Alternar a visibilidade do painel
        painelControle.SetActive(!painelControle.activeSelf);
    }

    void AlternarAuxilio()
    {
        // Ativar ou desativar o auxílio de mira
        auxilioAtivo = !auxilioAtivo;

        // Atualizar a interface (pode mudar a cor ou algum texto aqui)
        if (auxilioAtivo)
        {
            Debug.Log("Auxílio de mira ativado");
            // Colocar lógica para ativar o auxílio de mira
        }
        else
        {
            Debug.Log("Auxílio de mira desativado");
            // Colocar lógica para desativar o auxílio de mira
        }
    }

    void AlternarZoom()
    {
        // Alternar o estado do zoom 2x
        zoomAtivado = !zoomAtivado;

        // Atualizar o texto e comportamento de zoom
        if (zoomAtivado)
        {
            textoZoom.text = "Zoom: Ativado (2x 100%)";
            // Colocar a lógica de ativação do zoom (2x)
        }
        else
        {
            textoZoom.text = "Zoom: Desativado";
            // Colocar a lógica de desativação do zoom
        }
    }
}
