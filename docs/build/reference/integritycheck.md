---
title: "/INTEGRITYCHECK |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /INTEGRITYCHECK
dev_langs:
- C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99caec18162a7506b8b7a467eb7374b6fe4a38d9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2018
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

読み込み時にバイナリ イメージのデジタル署名を確認する必要があることを指定します。

> **/INTEGRITYCHECK****[: いいえ]**

## <a name="remarks"></a>コメント

DLL ファイルまたは実行可能ファイルのヘッダーで、このオプションは、Windows でイメージを読み込むために、メモリ マネージャーによるデジタル署名の確認を必要とするフラグを設定します。 Windows Vista 以前の Windows は、このフラグを無視します。 このオプションは、カーネル モード コードを実装する 64 ビット DLL には設定する必要があり、またすべてのデバイス ドライバーに推奨されます。 詳細については、次を参照してください。[カーネル モード コードの署名要件](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)です。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](../../build/reference/editbin-options.md)  
