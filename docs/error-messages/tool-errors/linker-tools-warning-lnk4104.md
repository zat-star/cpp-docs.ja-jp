---
title: "リンカー ツールの警告 LNK4104 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4104
dev_langs:
- C++
helpviewer_keywords:
- LNK4104
ms.assetid: ca6728db-d616-419a-a570-65e8445c6079
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b26286f375f54a20e1d3db534576f692179ade24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4104"></a>リンカー ツールの警告 LNK4104
シンボル 'symbol' のエクスポートがプライベートにする必要があります。  
  
 `symbol`次のいずれかになります。  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllGetDocumentation`  
  
-   `DllInitialize`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllRegisterServerExW`  
  
-   `DllUnload`  
  
-   `DllUnregisterServer`  
  
-   `RasCustomDeleteEntryNotify`  
  
-   `RasCustomDial`  
  
-   `RasCustomDialDlg`  
  
-   `RasCustomEntryDlg`  
  
 この警告では、dll インポート ライブラリを構築するときに出力し、上記の関数のいずれかのモジュール定義ファイルでプライベートとしてを指定せずにエクスポートします。 一般に、これらの関数は、OLE でのみ使用するエクスポートされます。 リンクされているライブラリを正しくプログラムがそれらへの呼び出しを行うときに、インポート ライブラリ内に配置することは異常な動作につながります。 PRIVATE キーワードの詳細については、次を参照してください。[エクスポート](../../build/reference/exports.md)です。