# 🛠️ Guia de Instalação Detalhado

Siga estes passos para configurar a Skill PO-UI no seu ambiente.

## 1. Clonar o Repositório
O código deve ser mantido localmente para que o servidor MCP possa ser executado via stdio.

```bash
cd C:\Ricardo\opencode
git clone https://github.com/ricardops34/po-ui.git skill-po-ui
cd skill-po-ui
```

## 2. Instalar Dependências e Compilar
Certifique-se de ter o Node.js v20+ instalado.

```bash
npm install
npm run build
```

## 3. Configuração na IDE

### Cursor
1. Abra as configurações do Cursor.
2. Vá em **General** > **MCP**.
3. Clique em **+ Add New MCP Server**.
4. Configure:
   - **Name**: `po-ui-skill`
   - **Type**: `stdio`
   - **Command**: `node C:/Ricardo/opencode/skill-po-ui/build/index.js`

### Claude Desktop
Edite seu arquivo `claude_desktop_config.json` (geralmente em `%APPDATA%\Claude\config.json` no Windows):

```json
{
  "mcpServers": {
    "po-ui-skill": {
      "command": "node",
      "args": ["C:/Ricardo/opencode/skill-po-ui/build/index.js"]
    }
  }
}
```

## 4. Testando a Skill
No chat da sua IA, você pode perguntar:
- "Liste os componentes disponíveis no PO-UI."
- "Como eu uso o componente PoTable? Me mostre a documentação."
- "Quais são as propriedades do PoNotificationService?"

A IA deverá utilizar as ferramentas `list_components` e `get_component_docs` automaticamente.
