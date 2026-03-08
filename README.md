# freelang-stdlib-multer

FreeLang v2 표준 라이브러리 — `multer.fl`

npm `multer` 완전 대체 구현. multipart/form-data 파일 업로드 처리.

## 파일

| 파일 | 설명 |
|------|------|
| `stdlib/multer.fl` | FreeLang 구현 (920줄) |
| `src/stdlib-multer.ts` | 네이티브 함수 (317줄) |

## 사용 예시

```freelang
import "stdlib/multer"

let upload = multer("uploads/")

app.post("/upload", upload.single("avatar"), fn(req, res) {
  let file = req.file
  res.json({ filename: file.filename, size: file.size })
})

app.post("/photos", upload.array("photos", 5), fn(req, res) {
  res.json({ count: arr.length(req.files) })
})
```

## 작업지시서 #8 구현 결과물
