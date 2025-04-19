# Comprime - Script de Compressão de Mídia

Um script em Python para compressão de arquivos de mídia (vídeo, imagem e áudio) com suporte a múltiplos formatos e opções de configuração.

## Características

- Compressão de vídeos, imagens e áudios
- Otimização automática para atingir o tamanho alvo
- Processamento paralelo de arquivos
- Verificação de integridade dos arquivos
- Backup automático dos arquivos originais
- Logging detalhado com diferentes níveis
- Interface de linha de comando amigável
- Barra de progresso durante a compressão
- Cache de arquivos comprimidos
- Compressão progressiva de vídeos grandes
- Suporte a GPU para compressão de vídeo
- Sistema de retry para operações que falham
- Logging com rotação de arquivos

## Requisitos

- Python 3.6 ou superior
- FFmpeg (para vídeos e áudios)
- ImageMagick (para imagens)
- Sistemas Unix-like (Linux, macOS, etc.)
- NVIDIA GPU (opcional, para compressão com GPU)

## Instalação

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/comprime.git
cd comprime
```

2. Instale as dependências do sistema:
```bash
# Ubuntu/Debian
sudo apt-get install ffmpeg imagemagick python3-pip

# macOS
brew install ffmpeg imagemagick python
```

3. Instale o pacote Python:
```bash
pip install -e .
```

## Uso

```bash
comprime [OPÇÕES]
```

### Opções

- `-i, --input DIR`: Diretório de entrada (padrão: diretório atual)
- `-o, --output DIR`: Diretório de saída (padrão: mesmo que entrada)
- `-q, --quality N`: Qualidade da compressão (0-51, padrão: 23)
- `-P, --preset NAME`: Preset de compressão (ultrafast...veryslow)
- `-b, --bitrate RATE`: Taxa de bits para áudio (padrão: 128k)
- `-j, --jobs N`: Número de jobs paralelos (padrão: 4)
- `-s, --silent`: Modo silencioso
- `-d, --debug`: Modo debug
- `-n, --no-backup`: Desativar backup dos arquivos originais
- `-c, --no-check`: Desativar verificação de integridade
- `-S, --no-space-check`: Desativar verificação de espaço em disco
- `-m, --max-size N`: Tamanho máximo de arquivo em MB (padrão: 1024)
- `--no-cache`: Desativar cache de arquivos comprimidos
- `--cache-dir DIR`: Diretório para cache (padrão: ~/.comprime_cache)
- `--cache-expiry N`: Dias para expiração do cache (padrão: 30)
- `--use-gpu`: Usar GPU para compressão de vídeo
- `--chunk-size N`: Tamanho dos chunks em MB (padrão: 100)
- `--log-file FILE`: Arquivo de log (opcional)
- `--max-log-size N`: Tamanho máximo do arquivo de log em MB (padrão: 10)
- `--log-backups N`: Número de arquivos de backup do log (padrão: 5)

### Exemplos

```bash
# Comprimir todos os arquivos no diretório atual
comprime

# Comprimir com qualidade específica
comprime -q 28 -P fast

# Comprimir em modo silencioso
comprime -s

# Comprimir com processamento paralelo
comprime -j 8

# Comprimir usando GPU
comprime --use-gpu

# Comprimir com cache personalizado
comprime --cache-dir /tmp/cache --cache-expiry 7

# Comprimir com logging em arquivo
comprime --log-file comprime.log --max-log-size 20
```

## Formatos Suportados

### Vídeo
- MP4, MKV, AVI, MOV, WMV, FLV, WebM

### Imagem
- JPG/JPEG, PNG, GIF, BMP, TIFF, WebP

### Áudio
- MP3, WAV, FLAC, AAC, OGG, M4A

## Cache

O script mantém um cache dos arquivos comprimidos para evitar reprocessamento desnecessário. O cache é armazenado em `~/.comprime_cache` por padrão e os arquivos expiram após 30 dias. Você pode personalizar essas configurações usando as opções `--cache-dir` e `--cache-expiry`.

## Compressão Progressiva

Para vídeos grandes, o script divide o arquivo em chunks menores e os processa em paralelo. O tamanho dos chunks pode ser ajustado com a opção `--chunk-size`.

## GPU

Se disponível, o script pode usar a GPU para acelerar a compressão de vídeos. Para ativar, use a opção `--use-gpu`.

## Logging

O script suporta diferentes níveis de logging:
- `debug`: Informações detalhadas para debugging
- `info`: Informações gerais sobre o processo
- `warning`: Avisos sobre possíveis problemas
- `error`: Erros que impedem a execução
- `silent`: Sem saída (exceto erros críticos)

Os logs podem ser salvos em arquivo com rotação automática. Use as opções `--log-file`, `--max-log-size` e `--log-backups` para configurar.

## Backup

Por padrão, o script cria backups dos arquivos originais adicionando `.original` ao nome do arquivo. Esta funcionalidade pode ser desativada com a opção `--no-backup`.

## Contribuindo

Contribuições são bem-vindas! Por favor, leia as diretrizes de contribuição antes de enviar pull requests.

## Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes. 