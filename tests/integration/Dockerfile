#
# Copyright Red Hat
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
FROM golang:1.21-alpine@sha256:2a1959ca3c229c72fbbee9643b88ef23d7859a7d18b60a0d94ee3d2923b49316

WORKDIR /registry-test

COPY . .

# Build the registry library and add to path
RUN cd /registry-test/registry-library && ./build.sh && cp /registry-test/registry-library/registry-library /usr/local/bin/registry-library

# Build the test binary
RUN /registry-test/build.sh

CMD /registry-test/devfile-registry-integration