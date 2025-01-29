## QRx - An agentic [QR Coding](https://github.com/RecursiveFaith/qrcoding) framework

![image](https://github.com/user-attachments/assets/75a1f23f-2aff-485b-8c7c-82f83a6e6f60)

> ***Ongoing research exploring:*** _Is it possible to create a single self-contained QR code that generates a Large Language Model (LLM) simulated Operating System (OS)? Can an LLM OS be used to generate full-dive mixed realities?_

<table>
  <thead>
    <tr>
      <th colspan=1><h3>Ollama (local)</h3></th>
      <th colspan=1><h3>OpenRouter (cloud)</h3></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        <h4><a href="https://ollama.sh">Ollama.sh</a></h4>
        <ul>
          <li>Default model: <a href="https://ollama.com/library/deepseek-r1:8b">deepseek/deepseek-r1</a>
          <li>Supports vision models</li>
          <li>Don't forget to <a href="https://github.com/ollama/ollama/blob/main/docs/faq.md#how-do-i-configure-ollama-server">enable CORS in Ollama</a></li>
        </ul>
      </td>
      <td>
        <h4><a href="https://openrouter.ai">OpenRouter.ai</a></h4>
        <ul>
          <li>Default model: <a href="https://openrouter.ai/deepseek/deepseek-r1">deepseek/deepseek-r1</a>
          <li>Supports vision models</li>
          <li>Free API keys available</li>
        </ul>
      </td>
    </tr>    
  </tbody>
</table>

### How to use the QR codes

- Create a `.html` file on your desktop or device
- Scan one of the QR codes above
- Copy the decoded string into the `.html`
- Open that file in a browser

Once the LLM OS bootstrap file above is created, you can then generate QR codes that use the `?prompt#filename` pattern to prompt and control your LLM OS using QR codes


### The database

Data is persisted using the browser's IndexedDB and localStorage APIs. By default `editor` is used as the table name. If you open these files directly in your browser without a server, the data will be mapped to that specific filename. Changing the filename would generate a new IndexedDB database (while keeping the old one)

For production use, it's recommended to run a server (todo: explain how)

### Creating a simple server

When loading a file directly in the browser it's loaded in the `file://` protocol, instead of `http://`. This works but minimizes the amount of Browser APIs you have available, and if you ever move or change the file name the data could be lost

It's recommended to generate your QR codes for a server. On Linux and Mac you can try `python3 -m http.server 9000`

## Development Notes

- To generate these QR Codes
  - I first compress the HTML with https://htmlcompressor.com/compressor
  - I then encode it into a QR code with https://www.nayuki.io/page/qr-code-generator-library
- QR Code limits:
  - Raw byte data: `17 to 2,953 bytes`
  - Numeric characters: `41 to 7,089 characters`
  - Alphanumeric: `25 to 4,296 characters`
