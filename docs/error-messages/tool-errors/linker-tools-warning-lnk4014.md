---
title: "リンカー ツールの警告 LNK4014 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4014
dev_langs: C++
helpviewer_keywords: LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9290c2412d6ae0e13afee22d6ba7f0784b29df1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4014"></a>リンカー ツールの警告 LNK4014
メンバー オブジェクト"objectname"を見つけることができません。  
  
 LIB が見つかりませんでした。`objectname`ライブラリです。  
  
 **/Remove**と**抽出/**オプションを削除するか、ファイルにコピーがメンバー オブジェクトの完全名を必要とします。 完全な名前には、元のオブジェクト ファイルのパスが含まれています。 ライブラリ内のメンバー オブジェクトの完全名を使用して DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md)または LIB [/list](../../build/reference/managing-a-library.md)です。