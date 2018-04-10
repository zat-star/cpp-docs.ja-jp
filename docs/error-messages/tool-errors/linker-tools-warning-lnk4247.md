---
title: リンカー ツールの警告 LNK4247 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 517605993199942f863faa78e14a022529214a64
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4247"></a>リンカー ツールの警告 LNK4247
エントリ ポイント 'decorated_function_name' は既に thread 属性です。' attribute' は無視されます。  
  
 指定されたエントリ ポイントが、 [/ENTRY (エントリ ポイント シンボル)](../../build/reference/entry-entry-point-symbol.md)、スレッドの属性を必要があるが、 [/CLRTHREADATTRIBUTE (CLR スレッド属性を設定)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)を指定した、別のスレッド モデルです。  
  
 リンカーでは、/CLRTHREADATTRIBUTE で指定した値が無視されます。  
  
 この警告を解決するには。  
  
-   ビルドから/CLRTHREADATTRIBUTE を削除します。  
  
-   ソース コード ファイルから属性を削除します。  
  
-   ソースと/CLRTHREADATTRIBUTE から、ビルドから両方属性を削除し、既定の CLR スレッド モデルをそのまま使用します。  
  
-   ソース内の属性を持つことに同意したことなど、/CLRTHREADATTRIBUTE に渡された値を変更します。  
  
-   /CLRTHREADATTRIBUTE に渡された値と、一致するように、ソース内の属性を変更します。  
  
 次の例には、LNK4247 が生成されます。  
  
```  
// LNK4247.cpp  
// compile with: /clr /c  
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console  
 [System::MTAThreadAttribute]  
void functionTitle (){}  
```