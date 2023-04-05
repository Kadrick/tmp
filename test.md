---
Title: Front
Date: 2022-12-21
Author: TestUser
Tag:
    - testing
    - math
    - code
---

## Table of contents

## Autolink literals

www.example.com, https://example.com, and contact@example.com.

## Footnote

A note[^1]

[^1]: Big note.

## Strikethrough

~one~ or ~~two~~ tildes.

## Table

| a     | b     |     c |   d   |
| ----- | :---- | ----: | :---: |
| holy  | moly  |  dely | ally  |
| test1 | test2 | test3 | test4 |

## Tasklist

-   [ ] to do
-   [x] done

-   Lists
-   [ ] todo
-   [ ] done

A table:

| a        | b        |
| -------- | -------- |
| contentA | contentB |

### lv.3 math

$$
Point_x Point_y \ddot{a} \sum_{
\begin{subarray}{l}
   i\in\Lambda\\
   0<j<n
\end{subarray}}
$$

수식 $ x_i y_i $ 테스트

#### lv4

##### lv 5

이미지 테스트

![이미지](/assets/img/github.png)

## long long long long long long long header

long longlonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglonglong contents

## Code

```go
/*
Copyright © 2022 NAME HERE <kbk2581553@gmail.com>

*/
package cmd

import (
	"errors"
	"fmt"

	"Glog/generator"

	"github.com/spf13/cobra"
)

var postCmd = &cobra.Command{
	Use:     "post",
	Short:   "Create New Post",
	Example: "Glog post [Title] [Author]",
	Args: func(cmd *cobra.Command, args []string) error {
		if len(args) != 2 {
			errorMsg := "unknown command \"post\" for \"Glog\".\n"
			return errors.New(errorMsg)
		}

		return nil
	},
	Run: func(cmd *cobra.Command, args []string) {
		fmt.Println("Create New Post...")

		filepath, err := generator.PostGenerator(args[0], args[1])
		if err != nil {
			fmt.Println("Failed to create file.")
			fmt.Println(err)
			return
		}

		fmt.Println("The file has been successfully created.")
		fmt.Printf("Save file path: %s\n", filepath)
		return
	},
}

func init() {
	rootCmd.AddCommand(postCmd)
}
```

[코드로](#code)
