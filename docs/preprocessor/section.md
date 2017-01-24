---
title: "セクション | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "section_CPP"
  - "vc-pragma.section"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "プラグマ, section"
  - "section プラグマ"
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# セクション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.obj ファイルにセクションを作成します。  
  
## 構文  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## 解説  
 このトピックでは、*セグメント*と*セクション*は同義の用語です。  
  
 セクションを定義すると、そのセクションはそれ以降のコンパイルで有効になります。  ただし、[\_\_declspec\(allocate\)](../Topic/allocate.md) を使用する必要があります。これを使用しないと、定義したセクションに何も配置されません。  
  
 *section\-name* は、セクションの名前となる必須パラメーターです。  標準セクション名と競合する名前は付けられません。  セクションを作成する場合に使用しない名前のリストについては、「[\/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。  
  
 省略可能なパラメーター `attributes` には、セクションに割り当てる 1 つ以上の属性をコンマで区切って指定します。  指定できる `attributes` は次のとおりです。  
  
 **read**  
 データの読み取り操作を有効にします。  
  
 **write**  
 データの書き込み操作を有効にします。  
  
 **execute**  
 コードを実行できるようにします。  
  
 **shared**  
 イメージを読み込んだすべてのプロセス間でセクションを共有します。  
  
 **nopage**  
 セクションをページング不可にします。Win32 デバイス ドライバー用です。  
  
 **nocache**  
 セクションをキャッシュ不可にします。Win32 デバイス ドライバー用です。  
  
 **discard**  
 セクションを破棄可能にします。Win32 デバイス ドライバー用です。  
  
 **remove**  
 セクションをメモリ非常駐として指定します。仮想デバイス ドライバー \(V*x*D\) のみ。  
  
 属性を指定しない場合、セクションには読み取り属性と書き込み属性が設定されます。  
  
## 使用例  
 次の例では、最初の命令でセクションとその属性を指定しています。  `__declspec(allocate)` を使用して宣言していないので、整数 `j` は `mysec` に追加されません。`j` はデータ セクションに配置されます。  整数 `i` は、その `__declspec(allocate)` ストレージ クラス属性の結果として `mysec` に追加されます。  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)