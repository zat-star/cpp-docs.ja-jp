---
title: file_status クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.workload:
- cplusplus
ms.openlocfilehash: 841fa34eba4878669b624620bb4f3205e9ff08e4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="filestatus-class"></a>file_status クラス

[file_type](../standard-library/filesystem-enumerations.md#file_type) とファイルの [perms](../standard-library/filesystem-enumerations.md#perms) をラップします。

## <a name="syntax"></a>構文

```cpp
class file_status;
```

## <a name="filestatusfilestatus"></a>file_status::file_status

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

## <a name="filestatusoperator"></a>file_status::operator =

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

この既定のメンバー代入演算子は想定どおりに動作します。

## <a name="type"></a>型

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

file_type を取得または設定します。

## <a name="permissions"></a>アクセス許可

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

ファイルのアクセス許可を取得または設定します。

セッターを使用して、ファイルを読み取り専用にしたり、読み取り専用属性を削除したりできます。

## <a name="requirements"></a>要件

**ヘッダー:** \<filesystem >

**Namespace:** std::experimental::filesystem、std::experimental::filesystem

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[path クラス](../standard-library/path-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
