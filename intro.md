import matplotlib.pyplot as plt
import pandas as pd

# 데이터 정의
data = {
    "사이즈": ["L (77)", "XL (1XL, 82)", "2XL (88)", "3XL (99)", "4XL (100~)"],
    "가슴둘레 (cm)": ["94~98", "98~102", "102~106", "106~112", "112~118"],
    "허리둘레 (cm)": ["72~76", "76~80", "80~88", "88~96", "96~104"],
    "엉덩이둘레 (cm)": ["98~102", "102~106", "106~110", "110~116", "116~122"]
}

df = pd.DataFrame(data)

# 이미지로 출력
fig, ax = plt.subplots(figsize=(8, 3))
ax.axis('off')
table = ax.table(cellText=df.values, colLabels=df.columns, cellLoc='center', loc='center')
table.auto_set_font_size(False)
table.set_fontsize(12)
table.scale(1.2, 1.5)
plt.title("여성 사이즈표 (한국 기준)", fontsize=14, weight='bold', pad=20)

plt.tight_layout()
plt.savefig("women_size_chart_korea.png", dpi=300)
plt.show()
