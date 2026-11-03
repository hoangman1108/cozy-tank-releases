# cozy-tank-releases — bản phát hành Cozy Tank

Repo công khai **chỉ chứa artifact phát hành** của game Cozy Tank:

- `CozyTank-<phiên bản>.dmg` — bản cài lần đầu (kéo vào Applications)
- `CozyTank-<phiên bản>.app.zip` — gói .app cho cơ chế tự cập nhật trong game
- `manifest.json` — thông tin bản mới nhất (phiên bản, ghi chú tiếng Việt, URL, sha256, thời điểm phát hành)

**Không có mã nguồn nào ở đây.** Mã nguồn nằm ở repo riêng tư `hoangman1108/cozy-tank`.
Repo này tồn tại vì: file tải release của repo riêng tư cần đăng nhập GitHub, còn manifest
và file cập nhật phải tải được **không cần token** để game tự kiểm tra/cập nhật.

Game đọc manifest tại:
`https://raw.githubusercontent.com/hoangman1108/cozy-tank-releases/main/manifest.json`
(fallback: `https://github.com/hoangman1108/cozy-tank-releases/releases/latest/download/manifest.json`)

Cập nhật mới do script `scripts/publish-update.sh` trong repo nguồn tạo ra
(nén .app bằng `ditto`, tính sha256, tạo manifest, `gh release create`).
