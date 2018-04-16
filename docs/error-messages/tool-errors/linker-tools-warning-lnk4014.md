---
title: "リンカー ツールの警告 LNK4014 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e0e0e87fb9c8e6006c62e07b7bb9b6435a22dd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4014"></a>リンカー ツールの警告 LNK4014
メンバー オブジェクト"objectname"を見つけることができません。  
  
 LIB が見つかりませんでした。`objectname`ライブラリです。  
  
 **/Remove**と**抽出/**オプションを削除するか、ファイルにコピーがメンバー オブジェクトの完全名を必要とします。 完全な名前には、元のオブジェクト ファイルのパスが含まれています。 ライブラリ内のメンバー オブジェクトの完全名を使用して DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md)または LIB [/list](../../build/reference/managing-a-library.md)です。