# Git Revert vs Reset

- `git revert` được dùng để tạo ra một commit mới có tác dụng đảo ngược một commit trước đó. Nó không thay đổi lịch sử commit, vì vậy an toàn khi làm việc nhóm hoặc khi đã đẩy code lên remote repo.

- `git reset` thì ngược lại, nó di chuyển HEAD về commit trước, đồng thời có thể xóa các commit sau nếu dùng `--hard`. Nó thay đổi lịch sử commit, vì vậy chỉ nên dùng khi làm việc cá nhân, trên nhánh chưa đẩy lên remote. Nếu dùng không cẩn thận, có thể mất code.

