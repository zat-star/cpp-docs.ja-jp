---
title: Windows ランタイムのサポートされていない CRT 関数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50a04dc63dfc5fbadce7721f5985e3190cdab506
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Windows ランタイムのサポートされていない CRT 関数

多くの C ランタイム (CRT) API は、Windows ランタイムで実行するユニバーサル Windows プラットフォーム (UWP) アプリでは使用できません。 これらのアプリは /ZW コンパイラ フラグを使用してビルドします。 サポートされない CRT 関数の一覧については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」をご覧ください。

すべての CRT API については、このドキュメントの「[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)」のセクションを参照してください。

## <a name="see-also"></a>参照

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
[関数リファレンス (アルファベット順)](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
