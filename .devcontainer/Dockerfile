# Microsoft ရဲ့ အရာအားလုံးနီးပါးပါဝင်တဲ့ Universal Dev Container image ကို အခြေခံအဖြစ် စတင်အသုံးပြုပါမယ်။
# ဒီထဲမှာ Python, Node.js, C/C++, Go, Java, Ruby, PHP တို့အတွက် tool တွေ ပါပြီးသားဖြစ်ပါတယ်။
FROM mcr.microsoft.com/devcontainers/universal:2

# Software တွေသွင်းဖို့ root user အဖြစ် ခေတ္တပြောင်းလဲအသုံးပြုပါမယ်။
USER root

# C# Development အတွက် လိုအပ်တဲ့ .NET 8 SDK ကို ထပ်ပြီး Install လုပ်ပါမယ်။
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends dotnet-sdk-8.0
    
# --- (Optional) သင်အသုံးများတဲ့ အခြား tool တွေကို ဒီနေရာမှာ ထပ်ထည့်နိုင်ပါတယ် ---

# ဥပမာ ၁: Python အတွက် poetry နဲ့ black formatter ကို သွင်းခြင်း
RUN pipx install poetry && pipx install black

# ဥပမာ ၂: Web Development အတွက် live-server ကို npm ကနေ global အဖြစ်သွင်းခြင်း
# 'vscode' user အနေနဲ့ သွင်းပေးရမှာဖြစ်လို့ 'su vscode -c "..."' command ကိုသုံးပါတယ်။
RUN su vscode -c "npm install -g live-server"

# Security အတွက် root မဟုတ်တဲ့ 'vscode' user ကို ပြန်ပြောင်းပေးထားပါမယ်။
USER vscode