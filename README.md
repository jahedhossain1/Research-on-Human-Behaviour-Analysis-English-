def preprocessing(text):
  text = toLower(text)
  text = remove_punc(text)
  text = remove_stopword(text)
  text = remove_punc_qut(text)
  text = stemming(text)
  text = tfidf.transform([text])

  return text

text = "Charging speed is remarkable, but it becomes heat."
print("Review: " ,text)
txt = preprocessing(text)
predict = rf_model.predict(txt)
if predict[0] == 1:
  print("Sentiment : Positive")
elif predict[0] == 0:
  print("Sentiment : Negative")
elif predict[0] == 4:
  print("Sentiment : Slightly Positive")
elif predict[0] == 3:
  print("Sentiment : Slightly Negative")
elif predict[0] == 2:
  print("Sentiment : Neutral")


Review:  Charging speed is remarkable, but it becomes heat.

                  Sentiment : Slightly Negative
  
