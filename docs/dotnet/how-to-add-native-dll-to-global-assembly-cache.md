---
title: "方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++], native"
  - "GAC (グローバル アセンブリ キャッシュ), 読み込み (ネイティブ DLL を)"
  - "ネイティブ DLL [C++]"
ms.assetid: 25e8d78a-b197-4269-b4e9-237a544ab3c8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ネイティブ DLL をグローバル アセンブリ キャッシュに追加する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ネイティブ DLL \(COM 以外\) はグローバル アセンブリ キャッシュに置くことができます。  
  
## 使用例  
 **\/ASSEMBLYLINKRESOURCE** を使用して、ネイティブ DLL をアセンブリに埋め込むことができます。  
  
 詳細については、「[\/ASSEMBLYLINKRESOURCE \(.NET Framework リソースへのリンク\)](../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)」を参照してください。  
  
```  
/ASSEMBLYLINKRESOURCE:MyComponent.dll  
```  
  
## 参照  
 [C\+\+ Interop \(暗黙の PInvoke\) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)