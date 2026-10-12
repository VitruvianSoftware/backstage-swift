# Copyright 2026 MyProject
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

# Start with the standard devcontainers base (Ubuntu-based)
FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install dependencies (direnv + curl for downloading bazelisk)
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       direnv curl ca-certificates \
    && rm -rf /var/lib/apt/lists/*

# Install bazelisk (latest release)
RUN curl -L https://github.com/bazelbuild/bazelisk/releases/latest/download/bazelisk-linux-amd64 \
      -o /usr/local/bin/bazelisk \
    && chmod +x /usr/local/bin/bazelisk \
    && ln -s /usr/local/bin/bazelisk /usr/local/bin/bazel

# Hook direnv into bash (default Codespaces shell)
RUN echo 'eval "$(direnv hook bash)"' >> /etc/bash.bashrc
