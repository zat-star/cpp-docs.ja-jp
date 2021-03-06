---
title: "リンカ ツール エラー LNK1256 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- xml
- LNK1256
dev_langs:
- C++
helpviewer_keywords:
- LNK1256
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbbb14e4f4fdef63b58bdef5ecafcfe0b045f412
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1256"></a>リンカ ツール エラー LNK1256
ALINK 処理に失敗しました : 理由  
  
 LNK1256 の一般的な理由は、アセンブリのバージョン番号が無効であることです。 値 65535 はアセンブリ バージョン番号のいずれの部分にも使用できません。 アセンブリのバージョンの有効な範囲は 0 ~ 65534 です。  
  
 また、指定されたキー コンテナーを ALINK が見つけることができなかった場合は、LNK1256 が発生する場合もあります。 キー コンテナーを削除し、再度追加する厳密な名前 CSP を使用して[Sn.exe (厳密名ツール)](/dotnet/framework/tools/sn-exe-strong-name-tool)です。  
  
 LNK1256 のもう 1 つの理由は、リンカーと Alink.dll の間でのバージョンの不一致です。 このことは、Visual Studio のインストールの破損によって発生する場合があります。 使用して**プログラムと機能**を修復または Visual Studio を再インストールするには、Windows コントロール パネルの します。  
  
 次の例では LNK1256 が生成されます。  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```