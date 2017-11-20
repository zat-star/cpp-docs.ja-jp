---
title: "リンカ ツール エラー LNK1309 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1309
dev_langs: C++
helpviewer_keywords: LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: febaeeeabdf045ee7d223b7514d63202ded1e99c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1309"></a>リンカ ツール エラー LNK1309
type1 モジュールが検出されました。スイッチ/CLRIMAGETYPE:type2 が無効です。  
  
 CLR イメージ タイプがと共に要求された**/CLRIMAGETYPE**が、1 つまたは複数のモジュールにその型と互換性がないので、リンカーはその種類のイメージを作成できませんでした。  
  
 たとえば、わかります LNK1309 を指定する場合**/CLRIMAGETYPE:safe**でビルドされたモジュールを渡すと**/clr: 純粋な**します。  
  
 [D] ptrustu .lib を使用して、部分的に信頼された CLR 純粋なアプリケーションをビルドしようとする場合は、LNK1309 も表示されます。 部分的に信頼されたアプリケーションを作成する方法については、次を参照してください。[する方法: CRT ライブラリ DLL に依存関係の削除によって部分的に信頼されたアプリケーションを作成](../../dotnet/create-a-partially-trusted-application.md)です。  
  
 詳細については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)と[/CLRIMAGETYPE (を指定する型の CLR イメージ)](../../build/reference/clrimagetype-specify-type-of-clr-image.md)です。