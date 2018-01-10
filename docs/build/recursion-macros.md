---
title: "再帰マクロ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8d9ef7f194151fb3259712759d0c29ed157d564
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="recursion-macros"></a>再帰マクロ
再帰マクロを使用すると、NMAKE を再帰的に呼び出します。 再帰的なセッションは、コマンドラインと環境変数マクロと Tools.ini の情報を継承します。 メイクファイルで定義された推論規則を引き継がないまたは**です。サフィックス**と**です。貴重な**仕様です。 再帰 (nmake の) セッションにマクロを渡すに再帰呼び出しの前に設定された環境変数を設定、再帰呼び出し用のコマンドでマクロを定義または Tools.ini でマクロを定義します。  
  
|マクロ|定義|  
|-----------|----------------|  
|**ください**|NMAKE の呼び出しに最初に使用するコマンド。<br /><br /> $(MAKE) マクロは、nmake.exe への完全なパスを提供します。|  
|**MAKEDIR**|NMAKE が呼び出されたときの現在のディレクトリ。|  
|**MAKEFLAGS**|現在有効になってオプションです。 として使用`/$(MAKEFLAGS)`です。  /F が含まれていないに注意してください。|  
  
## <a name="see-also"></a>参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)