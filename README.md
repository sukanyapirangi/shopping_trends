gender_count = df.value_counts('Gender')
gender_count = gender_count.to_frame().reset_index()

plt.figure(figsize=(8, 8))

ax = sns.barplot(data=gender_count, x='Gender', y='count')

for index, row in gender_count.iterrows():
    ax.text(index, row['count'], str(row['count']), ha='center', va='bottom', fontsize=12)

plt.title("Répartition des clients par sexe")
plt.xlabel("Sexe")
plt.ylabel("Compte")

plt.show()
