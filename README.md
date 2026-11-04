[README natas.md](https://github.com/user-attachments/files/34349298/README.natas.md)
<div align="center">

# 🗝️ OverTheWire: Natas — Writeups

![Status](https://img.shields.io/badge/status-em%20andamento-yellow)
![Level](https://img.shields.io/badge/n%C3%ADvel%20atual-natas10-blue)
![Tool](https://img.shields.io/badge/tool-Burp%20Suite-ff6633?logo=burpsuite&logoColor=white)
![OS](https://img.shields.io/badge/OS-Kali%20Linux-557C94?logo=kalilinux&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

Writeups pessoais dos primeiros níveis do wargame **[Natas](https://overthewire.org/wargames/natas/)**, da OverTheWire — exploração de vulnerabilidades web, resolvidos manualmente.

</div>

---

## 📌 Sobre

Resolvidos com o mínimo de ajuda possível (dicas de direção quando travado, nunca a resposta pronta), como parte de um estudo contínuo em segurança ofensiva aplicada a ambientes web. Repositório mantido como registro de estudo e portfólio técnico, dentro de uma trilha de aprendizado em infraestrutura, cloud e cibersegurança.

## 🧰 Stack usada

| Ferramenta | Uso |
|---|---|
| **Kali Linux** (VM, VMware Workstation Pro) | Ambiente de ataque |
| **Burp Suite Community** | Interceptação e manipulação de requisições HTTP |
| **DevTools (F12)** | Inspeção de código-fonte, cookies e storage |
| **CyberChef** | Decodificação de cadeias de transformação (hex, base64, reverse) |
| **curl** | Requisições diretas via terminal |

## 📈 Progresso

| # | Nível | Vulnerabilidade | Técnica principal |
|:---:|:---:|---|---|
| ✅ | [01](natas1-writeup.md) | Exposição em comentário HTML | DevTools (F12), bypass de bloqueio de botão direito |
| ✅ | [02](natas2-writeup.md) | Directory listing | Enumeração via recurso (`pixel.png`) + `curl` |
| ✅ | [03](natas3-writeup.md) | Security through obscurity | `robots.txt` → diretório "escondido" |
| ✅ | [04](natas4-writeup.md) | Controle de acesso via header | `Referer` forjado (Burp Repeater) |
| ✅ | [05](natas5-writeup.md) | Controle de sessão via cookie | Edição de cookie (`loggedin=0→1`) |
| ✅ | [06](natas6-writeup.md) | Exposição de include | Leitura direta de arquivo `.inc` |
| ✅ | [07](natas7-writeup.md) | LFI (Local File Inclusion) | Parâmetro `?page=` → leitura arbitrária de arquivo |
| ✅ | [08](natas8-writeup.md) | Encoding reversível | Reversão de `bin2hex` + `strrev` + `base64` |
| ✅ | [09](natas9-writeup.md) | OS Command Injection | Separador de comando (`;`) via `passthru()` |
| 🔄 | 10 | OS Command Injection (filtro) | Bypass de regex com `\n` |

## 💡 Conceito central que atravessa os níveis

> Nenhum dado controlado pelo **cliente** (URL, header, cookie, campo de formulário) deve ser a base de uma decisão de segurança no **servidor** sem validação real. Da mesma forma, "esconder" algo (arquivo, segredo, lógica) sem bloquear o acesso a ele não é proteção — é apenas ofuscação, quebrável assim que alguém souber onde olhar.

---

<div align="center">

*Writeups escritos para fixação de conceito — focam no raciocínio e na causa raiz de cada falha, não só no comando que resolve.*

</div>
