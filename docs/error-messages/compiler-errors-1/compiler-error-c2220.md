---
title: "コンパイラ エラー C2220 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2220
dev_langs: C++
helpviewer_keywords: C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc31519b2153c66ea9bab42f536ba7c6be5b2a10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2220"></a>コンパイラ エラー C2220
warning treated as error - no object file generated  
  
 [/WX](../../build/reference/compiler-option-warning-level.md)すべての警告をエラーとして扱うようにコンパイラに指示します。 エラーが発生したため、オブジェクトまたは実行可能ファイルは生成されませんでした。  
  
 このエラーのみが表示されるときに、 **/WX**フラグが設定され、コンパイル時に警告が発生します。 このエラーを解決するには、プロジェクトのすべての警告を除去する必要があります。  
  
### <a name="to-fix-use-one-of-the-following-techniques"></a>解決するには、次のいずれかの手法を使用します。  
  
-   プロジェクトの警告の原因となった問題を解決します。  
  
-   下の警告レベルをコンパイル — たとえば、使用して**/W3**の代わりに**/W4**です。  
  
-   使用して、[警告](../../preprocessor/warning.md)プラグマを無効にするか、特定の警告を抑制します。  
  
-   使用しない**/WX**をコンパイルします。