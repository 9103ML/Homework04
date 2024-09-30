def rms(samples):
  sq_samples = [s**2 for s in samples]
  avg_sqs = sum(sq_samples) / len(sq_samples)
  return avg_sqs ** 0.5

up_wv = []

WLEN = 1024
wx = range(0, len(wv03), WLEN)

sample_windows = []
for s_idx in wx:
  sample_windows.append(wv03[s_idx : s_idx + WLEN])

samples_rms = [rms(samples) for samples in sample_windows]

for window in samples_rms:
  

plt.plot(wv03)
plt.plot(wx, samples_rms, 'r')
plt.show()

plt.plot(fft_freqs, fft_energy)
plt.xlabel('Freq (Hz)')
plt.ylabel('FFT Energy')
plt.show()