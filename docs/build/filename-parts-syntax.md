---
title: "ファイル名分割構文 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a481f8c461cb4fddd4acb090edb2f2b5fd18636d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="filename-parts-syntax"></a>ファイル名分割構文
コマンド ファイル名分割構文では、(暗黙の依存する場合があります) を最初の依存ファイル名のコンポーネントを表します。 ファイル名コンポーネントは、ファイルのドライブ、パス、基本名、および拡張機能として、指定されたはディスク上に存在していないようです。 使用して**%s**を完全なファイル名を表します。 使用して**% &#124;**[*パーツ*]**F** (垂直バー文字に依存してパーセント記号) をファイル名の部分を表す場所*パーツ*以下の文字の 0 個以上にすることができますで任意の順序。  
  
|文字|説明|  
|------------|-----------------|  
|文字がありません。|完全な名前 (と同じ**%s**)|  
|**d**|ドライブ|  
|**p**|パス|  
|**f**|ファイルのベース名|  
|**e**|ファイル拡張子|  
  
 たとえば、ファイル名は c:\prog.exe とします。  
  
-   %s は c:\prog.exe されます。  
  
-   % &#124;です。F c:\prog.exe になります  
  
-   % (& a) #124; dF が c  
  
-   % (& a) #124; pF が c:\  
  
-   % (& a) #124; prog fF が  
  
-   % (& a) #124; exe eF が  
  
## <a name="see-also"></a>参照  
 [メイクファイルのコマンド](../build/commands-in-a-makefile.md)