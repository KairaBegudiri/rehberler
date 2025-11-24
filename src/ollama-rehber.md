Yerel bilgisayardan açık kaynaklı ChatGPT çalıştırma rehberi.

Minimum 10-12 GB VRAM'e sahip bir GPU kullanmanız şiddetle tavsiye edilir.

Bu rehber, Linux, MacOS ve Windows için geçerlidir.

## Linux
Öncelikle dağıtımınızın repolarından `ollama` paketini indirin. Eğer dağıtımınızda bu paketler yoksa aşağıdaki komutla indirebilirsiniz:
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

Eğer Arch Linux kullanıyorsanız buna eke olarak `ollama-cuda` paketini de indirmek isteyebilirsiniz.

Şimdi ollama'nın izin sorunu yaşamaması adına daemonu etkinleştirin:
```bash
sudo systemctl enable --now ollama
```

Bu noktadan sonra istediğiniz modeli indirmek var.

https://ollama.com/library ve https://huggingface.co üzerinden model bakabilirsiniz ancak bu rehberde gpt-oss'a deyineceğiz.
```bash
ollama run gpt-oss:20b
```

Bu çoğunuzun işini görecek güzel bir yapay zeka modeli ama eğer 3-4 tane RTX 3090'a sahipseniz `gpt-oss:120b` modelini de indirmek isteyebilirsiniz.
```bash
ollama run gpt-oss:120b
```

## Windows
https://ollama.com/download/OllamaSetup.exe adresinden kurulum dosyasını indirin 
Üstte bahsedilen https://ollama.com/library ve https://huggingface.co sitelerinde seçeceğiniz model haliyle burada da geçerli olacaktır.
Bu aşamadan sonra powershelli açmanız gerekmekte. 

```shell
ollama run gpt-oss:20b
```

Bu rehber, Ollama'yı Windows cihazlara kurmanızı önermez. Windows cihazlar sunucu görevi görmek için tasarlanmamıştır. MacOS veya Linux tercih etmeniz daha verimli olacaktır.

## MacOS

MacOS için dmg veya paket yöneticinizi kullanmanız gerekir. Her iki aşamada da kurulum aynıdır.

Terminali açın:
```zsh
brew install ollama
# Ardından;
ollama run gpt-oss:20b
```

Eğer bir kaç tane MacOS cihazı birbirine bağladıysanız `gpt-oss:120b` paketini kullanmanız da mümkün olacaktır
