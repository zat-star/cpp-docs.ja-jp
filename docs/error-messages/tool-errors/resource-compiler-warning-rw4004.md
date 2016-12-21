---
title: "リソース コンパイラの警告 RW4004 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RW4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RW4004"
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラの警告 RW4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ASCII character not equivalent to virtual key code  
  
 VIRTKEY 型のアクセラレータの中で仮想キー コードにリテラル文字列が使用されています。  
  
 この警告は無視して続行できますが、生成されたアクセラレータ キーが指定した文字列と一致しない場合があります。VIRTKEY では、ASCII アクセラレータとは異なるキー コードが使用されます。  
  
 リテラル文字列が構文的に有効な場合、WINDOWS.h 内の **VK\_\* \#define** の値を使用して必要なアクセラレータを取得することは可能です。