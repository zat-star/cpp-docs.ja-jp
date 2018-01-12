---
title: "コンパイラの警告 (レベル 1) C4656 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4656
dev_langs: C++
helpviewer_keywords: C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f342887bc91a48e9446f1403f1722c40b989546d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4656"></a>コンパイラの警告 (レベル 1) C4656
'symbol': データ型は、新しいまたは前回のビルド以降に変更されたまたは個所で異なる定義  
  
 前回成功したビルド以降に、データ型が追加されたか既存のデータ型が変更されました。これは、今までソース コードに含まれていなかったデータ型です。 エディット コンティニュは、既存のデータ型への変更をサポートしません。  
  
 この警告の後に必ず [致命的なエラー C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)が生成されます。 詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこの警告を削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **[デバッグ]** メニューの **[コード変更を適用]**をクリックします。  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには  
  
1.  **[デバッグ]** メニューの **[デバッグの停止]**をクリックします。  
  
2.  **[ビルド]** メニューの **[ビルド]**をクリックします。