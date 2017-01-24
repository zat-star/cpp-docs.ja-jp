---
title: "/CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute の追加) | Microsoft Docs"
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
  - "/CLRUNMANAGEDCODECHECK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRUNMANAGEDCODECHECK リンカー オプション"
  - "-CLRUNMANAGEDCODECHECK リンカー オプション"
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /CLRUNMANAGEDCODECHECK (SupressUnmanagedCodeSecurityAttribute の追加)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/CLRUNMANAGEDCODECHECK** は、マネージ コードからネイティブ DLL への、リンカーによって生成された `PInvoke` 呼び出しに対して、<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> を適用するかどうかを指定します。  
  
## 構文  
  
```  
/CLRUNMANAGEDCODECHECK[:NO]  
```  
  
## 解説  
 既定では、リンカーによって生成された `PInvoke` 呼び出しに対して、SuppressUnmanagedCodeSecurityAttribute が適用されます。  **\/CLRUNMANAGEDCODECHECK** を有効にすると、SuppressUnmanagedCodeSecurityAttribute が適用されません。  
  
 リンカーは、**\/clr** または **\/clr:pure** を指定してコンパイルされたオブジェクトだけに、この属性を適用します。  **\/clr:safe** を指定してコンパイルされたオブジェクトでは、`PInvoke` 呼び出しは生成されません。  詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 `PInvoke` 呼び出しは、リンカーが、マネージ呼び出し元からの参照に適合するマネージ シンボルは検出できないが、その参照に適合するネイティブ シンボルは検出できる場合に、リンカーによって生成されます。  `PInvoke` の詳細については、「[マネージ コードからのネイティブ関数の呼び出し](../../dotnet/calling-native-functions-from-managed-code.md)」を参照してください。  
  
 コードで <xref:System.Security.AllowPartiallyTrustedCallersAttribute> を使用する場合は、明示的に **\/CLRUNMANAGEDCODECHECK** を設定する必要があります。  イメージに SuppressUnmanagedCodeSecurity 属性および AllowPartiallyTrustedCallers 属性の両方が含まれる場合、セキュリティ上の脆弱性が生じる可能性があります。  
  
 SuppressUnmanagedCodeSecurityAttribute を使用する意味の詳細については、「[Security Optimizations](http://msdn.microsoft.com/ja-jp/cf255069-d85d-4de3-914a-e4625215a7c0)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[詳細\]** プロパティ ページをクリックします。  
  
5.  **\[CLR アンマネージ コード チェック\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)